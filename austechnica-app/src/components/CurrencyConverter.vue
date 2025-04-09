<script>
import CurrencyAPI from '@everapi/currencyapi-js';

export default {
    name: 'CurrencyConverter',
    data () {
        return {
            params: {
                base_currency: 'AUD',
                currencies: 'JPY,EUR,USD'
            },
            results: null,
            currencyApi: new CurrencyAPI('cur_live_ddEu9ijuITuP5VvC1XYN4cYSUAcFHsfppMXWv7RH')
        }
    },
    methods: {
        submit () {
            this.results = null;
            this.currencyApi.latest(this.params).then(response => {
                if (response.data) {
                    this.results = response.data;
                }
            });
        }
    }
}
</script>

<template>
    <div>
        <form
            class="mx-auto w-full max-w-sm bg-white shadow rounded-md p-5 space-y-3 text-sm"
            @submit.prevent="submit"
        >
            <div class="flex items-center justify-between space-x-5">
                <label for="base_currency_input">Base currency:</label>
                <input
                    v-model="params.base_currency"
                    type="text"
                    class="border-slate-300 border rounded-md py-2 px-4 text-sm"
                />
            </div>
            <div class="flex items-center justify-between space-x-5">
                <label for="currencies">Target currencies:</label>
                <input
                    v-model="params.currencies"
                    type="text"
                    class="border-slate-300 border rounded-md py-2 px-4 text-sm"
                />
            </div>
            <button
                type="submit"
                class="bg-slate-800 text-white rounded-md py-2 px-4 mx-auto relative block"
            >Get Latest Rates</button>
        </form>
        <div
            v-if="results"
            class="mx-auto my-5 w-full max-w-sm bg-white shadow rounded-md px-5 py-3 text-sm divide-y divide-dotted divide-slate-300"
        >
            <div
                v-for="result of results"
                :key="result.code"
                class="flex items-center justify-between py-2"
            >
                <strong>{{ result.code }}</strong>
                <span>{{ result.value }}</span>
            </div>
        </div>
    </div>
</template>
