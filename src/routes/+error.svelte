<script lang="ts">
  import { page } from "$app/stores";

  const error = $page.error!;
  const status = $page.status!;

  const customErrorMessages: { [k: number]: string } = {
    404: "Couln't find that page..."
  };

  const message =
    status in customErrorMessages ? customErrorMessages[status] : error.message || "Page not found";
</script>

<main class="flex h-full items-center justify-center backdrop-blur-xl">
  <div class="max-w-md rounded-lg bg-slate-800 p-8 shadow-lg">
    <h1 class="mb-4 text-7xl font-bold">Oh no! A {status} error occured.</h1>
    <p class="">{message}</p>
  </div>
</main>
