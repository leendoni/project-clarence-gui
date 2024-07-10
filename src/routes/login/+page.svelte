<script lang="ts">
	import { Button } from '$lib/components/ui/button/index.js';
	import { Input } from '$lib/components/ui/input/index.js';
	import { Label } from '$lib/components/ui/label/index.js';
</script>

<div class="h-screen w-screen overflow-x-hidden lg:grid lg:grid-cols-2">
	<div class="flex items-center justify-center py-12">
		<div class="mx-auto grid w-[350px] gap-6">
			<div class="grid gap-2 text-center">
				<h1 class="text-3xl font-bold">STIB-DSCF</h1>
				<p class="text-muted-foreground text-balance">
					Digital Student Clearance Form for STI College Baliuag
				</p>
			</div>
			<hr />
			<div class="grid gap-4 py-4">
				<div class="grid grid-cols-4 items-center gap-4">
					<Label for="username" class="text-right">Student No.</Label>
					<Input id="username" class="col-span-3" placeholder="3000031859" required />
				</div>
				<div class="grid grid-cols-4 items-center gap-4">
					<Label for="password" class="text-right">Password</Label>
					<Input id="password" class="col-span-3" type="password" placeholder="********" required />
				</div>
			</div>
			<Button type="submit" class="w-full">Login</Button>
			<div class="text-muted-foreground text-center text-sm">
				Don&apos;t have an account?
				<a href="##" class="underline"> Sign up </a>
			</div>
			<hr />
		</div>
	</div>
	<div class="bg-muted hidden lg:block">
		<img
			src="/placeholder.svg"
			alt="placeholder"
			width="1920"
			height="1080"
			class="h-full w-full object-cover dark:brightness-[0.2] dark:grayscale"
		/>
	</div>
</div>
