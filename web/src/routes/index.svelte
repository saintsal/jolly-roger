<script context="module">
  // export const hydrate = false;
</script>

<script lang="ts">
  import {url} from '$lib/utils/url';
  const name = 'Jolly Roger';

  function _select(elem: HTMLElement) {
    const range = document.createRange();
    const selection = window.getSelection();
    range.selectNodeContents(elem);
    console.log({selection: range.toString()});
    // eslint-disable-next-line @typescript-eslint/no-explicit-any
    (selection as any).removeAllRanges();
    // eslint-disable-next-line @typescript-eslint/no-explicit-any
    (selection as any).addRange(range);
  }
  function select(e: MouseEvent) {
    _select(e.currentTarget as HTMLElement);
  }
</script>

<main>
  <section>
    <header>
      <img src="images/logo.svg" alt={name} style="width:256px;height:256px;" />
      <h1>
        {name}
      </h1>
      <p>Production-Ready Template To Build Decentralised Applications</p>
      <a href={url('demo/')} label="Try the Demo!"><strong>Demo</strong></a>
      <a href="https://github.com/wighawag/jolly-roger" label="Clone on github!"><em>Github</em></a>
    </header>
  </section>
  <section>
    <header>
      <h2>Use it</h2>

      <code id="jolly-roger-command" on:click={select}>npx degit wighawag/jolly-roger your-app-folder</code>
      <p>
        Find out more on
        <a href="https://github.com/wighawag/jolly-roger#readme" target="_blank" rel="noopener">github</a>
      </p>
    </header>
  </section>

  <section>
    <header>
      <h2>Showcase</h2>
      <p>Some apps built using jolly-roger</p>
    </header>

    <aside>
      <a href="https://bleeps.art" target="_blank"
        ><img class="h-48 w-full object-cover" src="https://bleeps.art/preview.png" alt="bleeps.art" /></a
      >
      <a href="https://bleeps.art" target="_blank" class="underline"> bleeps.art </a>
      <p class="text-xl font-semibold text-gray-900 dark:text-gray-100">The Bleeps DAO and Its Fully Onchain Sounds</p>
      <p class="mt-3 text-base text-gray-700 dark:text-gray-300">
        The First Composable Sounds Fully Generated On-Chain With Zero Externalities, no backend, no ipfs, no
        client-code, and a melody minter where some of the proceeds goes to the Bleeps DAO and its members
      </p>
      <p class="mt-3 text-base text-gray-500">
        Source code available <a href="https://github.com/wighawag/bleeps" target="_blank" class="underline">here</a>
      </p>
    </aside>

    <aside>
      <a href="https://mandalas.eth.limo" target="_blank"
        ><img class="h-48 w-full object-cover" src="https://mandalas.eth.limo/preview.png" alt="mandalas.eth" /></a
      >
      <a href="https://mandalas.eth.limo" target="_blank" class="underline"> mandalas.eth </a>
      <p class="text-xl font-semibold text-gray-900 dark:text-gray-100">
        On-chain Generative Bitmaps With Zero Externalities
      </p>
      <p class="mt-3 text-base text-gray-700 dark:text-gray-300">
        The First On-Chain Generative Art Project to make full use of token URI to remove all external dependencies. It
        generates SVG and Bitmap from the smart contract directly.
      </p>
      <p class="mt-3 text-base text-gray-500">
        Source code available <a href="https://github.com/wighawag/mandalas" target="_blank" class="underline">here</a>
      </p>
    </aside>

    <aside>
      <a href="https://conquest.eth.limo" target="_blank"
        ><img class="h-48 w-full object-cover" src="https://conquest.eth.limo/preview.png" alt="conquest.eth" /></a
      >
      <p class="text-xl font-medium text-pink-600">
        <a href="https://conquest.eth.limo" target="_blank" class="underline"> conquest.eth </a>
      </p>
      <div class="block mt-2">
        <p class="text-xl font-semibold text-gray-900 dark:text-gray-100">
          A Game of Strategy and Diplomacy Running on the EVM
        </p>
        <p class="mt-3 text-base text-gray-700 dark:text-gray-300">
          An unstoppable game of strategy and diplomacy running on the EVM. It allows player to collaborate through
          on-chain alliances while remaining sovereign. A first of its kind.
        </p>
        <p class="mt-3 text-base text-gray-500">Source code not yet available</p>
      </div>
    </aside>
  </section>

  <section>
    <header>
      <h2>Features</h2>
    </header>
    <aside>
      <strong>All included</strong>
      <p>
        This template include setup for smart contracts, subgraph (contract api) and frontend. All is setup as a
        monorepo with a shared common library.
      </p>
    </aside>
    <aside>
      <strong> PWA ready: 100% Lighthouse score </strong>
      <p>
        The web app is fully PWA compliant, with offline caching, etc... The javascript code necessary to launch the app
        is less than 50kB (15kB compressed), including the home page content. The rest is loaded on demand.
      </p>
    </aside>
    <aside>
      <strong> Great Dev experience </strong>
      <p>
        <a class="text-blue-600" href="https://hardhat.org" target="_blank" rel="noopener">Hardhat</a>
        for contracts,
        <a class="text-blue-600" href="https://github.com/wighawag/hardhat-deploy" target="_blank" rel="noopener"
          >hardhat-deploy</a
        >
        for contract deployment,
        <a class="text-blue-600" href="https://thegraph.com" target="_blank" rel="noopener">The Graph</a>
        for contract api,
        <a class="text-blue-600" href="https://svelte.dev" target="_blank" rel="noopener">svelte + Svelte Kit</a>
        for frontend with HMR (Hot Module Replacement) and production build.
      </p>
    </aside>
    <aside>
      <strong> Everything Hot Reload </strong>
      <p>
        On contract changes, contract get to keep their address and code get updated automatically. On frontend changes,
        module get replaced using blazing fast
        <a class="text-blue-600" href="https://vite.dev" target="_blank" rel="noopener">Vite</a>
        es module hot reload. On subgraph changes, the graph get updated and reexecuted.
      </p>
    </aside>
    <aside>
      <strong> Fully IPFS Ready </strong>
      <p>
        Fully IPFS ready with proper url routing. The web app works on both IPFS urls and ENS/DNS urls. PWA works on
        IPFS too with scoped service workers.
      </p>
    </aside>
    <aside>
      <strong> All in Typescript </strong>
      <p>The whole app including contracts tests, is written in typescript.</p>
    </aside>
    <aside>
      <strong> Code Splitting and Tree Shaking </strong>
      <p>
        By using Svelte Kit (and so Vite) and ES modules, the frontend benefit from code splitting an dynamic imports as
        well as tree shaking.
      </p>
    </aside>
    <aside>
      <strong> VSCode Setup </strong>
      <p>
        The repo is setup as a vscode workspace with recommended plugins. Execute tests from the editor. Auto format,
        etc...
      </p>
    </aside>
    <aside>
      <strong> One command deploy </strong>
      <p>
        Everything is setup, except for the private ENV variable to deploy the contracts, the subgraph and the web app,
        all at once. It also include <a class="text-blue-600" href="https://fleek.co" target="_blank" rel="noopener"
          >fleek</a
        > config for automatic web deployment on ipfs.
      </p>
    </aside>
  </section>
</main>
