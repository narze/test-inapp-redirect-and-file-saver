<script>
  import InAppSpy from "inapp-spy";
  import { on } from "svelte/events";
  import FileSaver from "file-saver";
  const { isInApp, appKey, appName } = InAppSpy();

  console.log({ isInApp, appKey, appName });

  function saveFile() {
    FileSaver.saveAs("/save_me.svg", "image.svg");
  }

  function saveExternalFile() {
    FileSaver.saveAs("https://httpbin.org/image", "image.jpg");
  }
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
<button on:click={saveFile}>Save internal image with FileSaver</button>
<button on:click={saveExternalFile}>Save external image with FileSaver</button>

<img src="https://placehold.co/600x400?text=Try Save me!" alt="" />
