<script lang="ts">
    import { onMount, onDestroy } from "svelte";

    interface Dog {
        id: number;
        name: string;
        breed: string;
    }
    interface Breed {
        id: number;
        name: string;
    }

    let dogs: Dog[] = [];
    let breeds: Breed[] = [];
    let selectedBreed: number | null = null;
    let onlyAvailable = false;
    let loading = true;
    let error: string | null = null;
    let intervalId: ReturnType<typeof setInterval> | null = null;

    const fetchBreeds = async () => {
        try {
            const res = await fetch("/api/breeds");
            if (res.ok) {
                breeds = await res.json();
            }
        } catch (e) {
            // ignore breed fetch errors for now
        }
    };

    const fetchDogs = async () => {
        loading = true;
        error = null;
        try {
            let url = "/api/dogs";
            const params: string[] = [];
            if (selectedBreed) params.push(`breed_id=${selectedBreed}`);
            if (onlyAvailable) params.push("status=AVAILABLE");
            if (params.length) url += "?" + params.join("&");
            const res = await fetch(url);
            if (res.ok) {
                dogs = await res.json();
            } else {
                error = "Failed to fetch dogs";
            }
        } catch (e) {
            error = "Error fetching dogs";
        } finally {
            loading = false;
        }
    };

    const handleBreedChange = (e: Event) => {
        selectedBreed = +(e.target as HTMLSelectElement).value || null;
        fetchDogs();
    };

    const handleAvailableChange = (e: Event) => {
        onlyAvailable = (e.target as HTMLInputElement).checked;
        fetchDogs();
    };

    onMount(() => {
        fetchBreeds();
        fetchDogs();
        intervalId = setInterval(fetchDogs, 5000);
    });

    onDestroy(() => {
        if (intervalId) clearInterval(intervalId);
    });
</script>

<div class="flex items-center gap-4 mb-6">
    <label class="text-slate-300">
        Breed:
        <select class="bg-slate-700 text-slate-100 rounded px-2 py-1 ml-2" on:change={handleBreedChange} bind:value={selectedBreed}>
            <option value="">All</option>
            {#each breeds as breed}
                <option value={breed.id}>{breed.name}</option>
            {/each}
        </select>
    </label>
    <label class="flex items-center text-slate-300">
        <input type="checkbox" class="mr-2 accent-green-500" on:change={handleAvailableChange} bind:checked={onlyAvailable} />
        Only show available dogs
    </label>
</div>

{#if loading}
    <div class="text-slate-400">Loading...</div>
{:else if error}
    <div class="text-red-400">{error}</div>
{:else if dogs.length === 0}
    <div class="text-slate-400">No dogs found.</div>
{:else}
    <ul class="grid grid-cols-1 md:grid-cols-2 gap-4">
        {#each dogs as dog}
            <li class="bg-slate-800/70 border border-slate-700 rounded-xl p-4 text-slate-100">
                <div class="font-bold text-lg">{dog.name}</div>
                <div class="text-slate-400">{dog.breed}</div>
                <!-- Add more dog info as needed -->
            </li>
        {/each}
    </ul>
{/if}