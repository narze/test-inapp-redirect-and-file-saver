<script>
  import InAppSpy from "inapp-spy";
  import { on } from "svelte/events";
  const { isInApp, appKey, appName } = InAppSpy();

  console.log({ isInApp, appKey, appName });
</script>

<h1>Check in-app browser</h1>

<p>isInApp: {isInApp}</p>
<p>appKey: {appKey}</p>
<p>appName: {appName}</p>

<button
  on:click={() => window.open(window.location.href, "_system", "location=yes")}
  >Open in _system browser</button
>
<button on:click={() => window.open(window.location.href, "_blank")}
  >Open in _blank</button
>

<img src="https://placehold.co/600x400?text=Try Save me!" alt="" />
