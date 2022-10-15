<script lang="ts">
  type LinkInfo = {href: string; title: string};
  export let links: LinkInfo[];
  import NavLink from './NavLink.svelte';
  import Loading from '../Loading.svelte';
  import {urlOfPath} from '$lib/utils/url';
  import {page, navigating} from '$app/stores';
</script>

<!-- {JSON.stringify($page, null, '  ')} -->

<!-- {JSON.stringify($navigating, null, '  ')} -->

  <nav><ul>

  {#each links as link}
    <li>
    <a href={link.href} active={urlOfPath(link.href, $page.url.pathname)}>
      {link.title}
      </a>
    </li>
  {/each}

  </ul></nav>

{#if $navigating}
  <Loading />
{/if}
