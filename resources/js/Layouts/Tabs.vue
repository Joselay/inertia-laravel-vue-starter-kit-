<template>
    <div>
        <div class="sm:hidden">
            <label for="tabs" class="sr-only">Select a tab</label>
            <select
                id="tabs"
                name="tabs"
                class="block w-full border-gray-300 rounded-md focus:border-indigo-500 focus:ring-indigo-500"
            >
                <option
                    v-for="tab in tabs"
                    :key="tab.name"
                    :selected="tab.current"
                >
                    {{ tab.name }}
                </option>
            </select>
        </div>
        <div class="hidden sm:block">
            <nav class="flex space-x-4" aria-label="Tabs">
                <a
                    v-for="tab in tabs"
                    :key="tab.name"
                    :href="tab.href"
                    :class="[
                        tab.current
                            ? 'bg-gray-100 text-gray-700'
                            : 'text-gray-500 hover:text-gray-700',
                        'rounded-md px-3 py-2 text-sm font-medium',
                    ]"
                    :aria-current="tab.current ? 'page' : undefined"
                    >{{ tab.name }}</a
                >
            </nav>
        </div>
    </div>
</template>

<script setup>
const tabs = [
    { name: "My Account", href: "#", current: false },
    { name: "Company", href: "#", current: false },
    { name: "Team Members", href: "#", current: true },
    { name: "Billing", href: "#", current: false },
];
</script>
