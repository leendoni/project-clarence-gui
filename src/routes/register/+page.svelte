<script lang="ts">
	import { Button } from '$lib/components/ui/button/index.js';
	import { Input } from '$lib/components/ui/input/index.js';
	import { Label } from '$lib/components/ui/label/index.js';
</script>

<div class="h-screen w-screen overflow-x-hidden lg:grid lg:grid-cols-2">
	<div class="flex items-center justify-center py-12">
		<div class="mx-auto grid w-[350px] gap-6">
			<hr />
			<p class="text-2xl font-bold">Student Registration</p>
			<div class="grid gap-4 py-4">
				<div class="grid grid-cols-4 items-center gap-4">
					<Label for="lastName" class="text-right">Last Name</Label>
					<Input id="lastName" class="col-span-3" placeholder="Dela Cruz" />
				</div>
				<div class="grid grid-cols-4 items-center gap-4">
					<Label for="firstName" class="text-right">First Name</Label>
					<Input id="firstName" class="col-span-3" placeholder="Juan" required />
				</div>
				<div class="grid grid-cols-4 items-center gap-4">
					<Label for="studNum" class="text-right">Student No.</Label>
					<Input id="studNum" class="col-span-3" placeholder="3000031859" required />
				</div>
				<div class="grid grid-cols-4 items-center gap-4">
					<Label for="password" class="text-right">Password</Label>
					<Input id="password" class="col-span-3" type="password" placeholder="********" required />
				</div>
				<div class="grid grid-cols-4 items-center gap-4">
					<Label for="password" class="text-right">Confirm Password</Label>
					<Input id="password" class="col-span-3" type="password" placeholder="********" required />
				</div>
				<div class="grid grid-cols-4 items-center gap-4">
					<Label for="sectCode" class="text-right">Section Code</Label>
					<Input id="sectCode" class="col-span-3" placeholder="COL_BSIT-1A" required />
				</div>
			</div>
			<Button type="submit" class="w-full">Register</Button>
			<div class="text-center text-sm">Your account will be valid for one (1) academic year.</div>
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
