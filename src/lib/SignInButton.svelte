<script lang="ts">
  export let provider: {
    id: string
    name: string
    signinUrl: string
    callbackUrl?: string
  }
</script>

<form action={provider.signinUrl} method="POST">
  <input type="hidden" name="providerId" value={provider.id} />
  {#if provider.callbackUrl}
    <input type="hidden" name="callbackUrl" value={provider.callbackUrl} />
  {/if}
  <button type="submit" class="button">
    <slot>Sign in with {provider.name}</slot>
  </button>
</form>
