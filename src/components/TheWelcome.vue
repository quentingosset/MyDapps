<script setup>
import { createWeb3Modal, defaultConfig } from '@web3modal/ethers5/vue'
// 1. Get projectId at https://cloud.walletconnect.com
const projectId = 'YOUR_PROJECT_ID'

// 2. Set chains
const mainnet = {
  chainId: 1,
  name: 'Ethereum',
  currency: 'ETH',
  explorerUrl: 'https://etherscan.io',
  rpcUrl: 'https://cloudflare-eth.com'
}

// 3. Create your application's metadata object
const metadata = {
  name: 'My Website',
  description: 'My Website description',
  url: 'https://mywebsite.com', // url must match your domain & subdomain
  icons: ['https://avatars.mywebsite.com/']
}

// 4. Create Ethers config
const ethersConfig = defaultConfig({
      /*Required*/
      metadata,

      /*Optional*/
      enableEIP6963: true, // true by default
      enableInjected: true, // true by default
      enableCoinbase: true, // true by default
      rpcUrl: '...', // used for the Coinbase SDK
      defaultChainId: 1, // used for the Coinbase SDK
    });

    // 5. Create a Web3Modal instance
const modal = createWeb3Modal({
  ethersConfig,
  chains: [mainnet],
  projectId,
  enableAnalytics: true, // Optional - defaults to your Cloud configuration
  enableOnramp: true // Optional - false as default
})
</script>

<template>
  <main>
    <header class="p-3 text-bg-dark">
      <div class="container">
        <div class="d-flex flex-wrap align-items-center justify-content-center justify-content-lg-start">
          <div class="text-end">
            <w3m-button />
          </div>
        </div>
      </div>
    </header>
    <div class="container-fluid vh-100 w-100">
      <iframe src="https://app.aave.com/" style="border: 0; width: 100%; height: 100%"></iframe>
    </div>
  </main>
</template>
