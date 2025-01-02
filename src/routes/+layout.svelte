<script>
  import { goto } from "$app/navigation";
  import { mount } from "svelte";
  import * as Avatar from "$lib/components/ui/avatar/index.js";
  import { Badge } from "$lib/components/ui/badge/index.js";
  import { Separator } from "$lib/components/ui/separator/index.js";
  import { Mail } from 'lucide-svelte';
  import { Phone } from 'lucide-svelte';
  import "../app.css";
  // @ts-ignore
  import { ModeWatcher, setMode } from "mode-watcher";
  let { children } = $props();

  setMode("dark"); // auto set dark mode
</script>

<ModeWatcher />

<div class="flex h-screen gap-x-10 mx-8 text-center items-center">
  <div class="flex flex-col gap-4 grow-0 px-16 py-14 border rounded-xl items-center">
    <div class="border p-3 rounded-2xl bg-zinc-800">
      <Avatar.Root class="size-20">
        <Avatar.Image src="https://github.com/shadcn.png" alt="@shadcn" />
        <Avatar.Fallback>CN</Avatar.Fallback>
      </Avatar.Root>
    </div>
	<h2 class="font-semibold text-xl">Thavith Javisooth</h2>
	<div class="flex">
		<Badge variant="secondary">Web Developer</Badge>
	</div>
	<Separator/>
	<div class="pt-3 flex gap-3 flex-col">
		<div class="flex items-center">
			<div class="p-2 bg-zinc-800 rounded-xl">
				<Mail/>
			</div>
			<span class="px-2">:</span>
			<p class="">thavith501@gmail.com</p> 
		</div>
		<div class="flex items-center">
			<div class="p-2 bg-zinc-800 rounded-xl">
				<Phone/>
			</div>
			<span class="px-2">:</span>
			<p class="">094-468-7700</p>
		</div>
	</div>
  </div>
  <div class="grow border">
    {@render children()}
  </div>
</div>
