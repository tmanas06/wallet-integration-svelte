<script lang="ts">
    import { PrivateKey } from '@bsv/sdk';
    
    let WIF: string = '';
    let address: string = '';
    
    function createKeys() {
        const privKey = PrivateKey.fromRandom();
        WIF = privKey.toWif();
        console.log("Private Key WIF format is ", WIF);
        address = privKey.toAddress();
        console.log("Your bitcoin address is ", address);
    }
</script>

<section class="flex flex-col items-center justify-center min-h-screen bg-gray-100 dark:bg-gray-900">
    <div class="p-8 bg-white dark:bg-gray-800 shadow-lg rounded-lg text-center">
        <h1 class="text-2xl font-bold mb-4 text-gray-800 dark:text-gray-100">Generate New Wallet Keys</h1>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded mb-6" on:click={createKeys}>
            Generate
        </button>
        {#if WIF && address}
            <div class="text-left">
                <p class="text-lg text-gray-800 dark:text-gray-100"><strong>Private Key (WIF format):</strong> {WIF}</p>
                <p class="text-lg text-gray-800 dark:text-gray-100"><strong>Your Bitcoin Address:</strong> {address}</p>
            </div>
        {/if}
    </div>
</section>

<style>
    button:disabled {
        background-color: #a0aec0;
        cursor: not-allowed;
    }
</style>
