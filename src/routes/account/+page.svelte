<script lang="ts">
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Button, buttonVariants } from '$lib/components/ui/button/index.js';
	import * as Card from '$lib/components/ui/card/index.js';
	import * as Dialog from '$lib/components/ui/dialog/index.js';
	import * as DropdownMenu from '$lib/components/ui/dropdown-menu/index.js';
	import { Input } from '$lib/components/ui/input/index.js';
	import { Label } from '$lib/components/ui/label/index.js';
	import * as Pagination from '$lib/components/ui/pagination';
	import * as Table from '$lib/components/ui/table/index.js';
	import * as Tabs from '$lib/components/ui/tabs/index.js';
	import { Textarea } from '$lib/components/ui/textarea/index.js';

	import Activity from 'lucide-svelte/icons/activity';
	import CircleUser from 'lucide-svelte/icons/circle-user';
	import CircuitBoard from 'lucide-svelte/icons/circuit-board';
	import GraduationCap from 'lucide-svelte/icons/graduation-cap';
	import Home from 'lucide-svelte/icons/home';
	import List from 'lucide-svelte/icons/list';
	import Settings from 'lucide-svelte/icons/settings';
	import Smartphone from 'lucide-svelte/icons/smartphone';
	import UserCheck from 'lucide-svelte/icons/user-check';
	import UserX from 'lucide-svelte/icons/user-x';
	import Users from 'lucide-svelte/icons/users';
	import Pencil from 'lucide-svelte/icons/pencil';
	import Save from 'lucide-svelte/icons/save';
</script>

<div class="flex h-screen flex-col place-items-center items-center overflow-x-hidden">
	<!-- main space -->
	<div class="h-screen flex-col lg:w-1/2">
		<div class="flex h-14 w-full flex-row items-center gap-4 border-b bg-white px-4">
			<DropdownMenu.Root>
				<DropdownMenu.Trigger asChild let:builder>
					<Button builders={[builder]} variant="secondary" size="icon" class="rounded-full">
						<CircleUser class="h-5 w-5" />
						<span class="sr-only">Toggle user menu</span>
					</Button>
				</DropdownMenu.Trigger>
				<DropdownMenu.Content align="end">
					<div class="flex flex-col p-2">
						<p class="text-sm font-bold">StudentNameHere</p>
						<p class="text-xs">StudentNumberHere</p>
						<p class="text-xs">StudentSectionHere</p>
					</div>
					<DropdownMenu.Separator />
					<DropdownMenu.Item>Logout</DropdownMenu.Item>
				</DropdownMenu.Content>
			</DropdownMenu.Root>
			<p class="text-base font-bold">Student Clearance Form</p>
		</div>
		<!-- main -->
		<div class="grid h-screen w-full justify-between gap-2 p-2">
			<!-- student info -->
			<div class="w-full">
				<Card.Root>
					<Card.Header class="flex flex-row items-center justify-between space-y-0 pb-4">
						<Card.Title class="text-xl font-bold">Clearance</Card.Title>
						<Badge variant="outline">LIVE UPDATES</Badge>
					</Card.Header>
					<Card.Content>
						<div class="flex gap-2">
							<!-- masterlist -->
							<Card.Root class="col-span-4">
								<Card.Header class="flex flex-col gap-2">
									<div class="flex flex-row">
										<Card.Title>Student Clearance</Card.Title>
										<div class="flex w-full flex-row place-content-end gap-2">
											<Button variant="outline" size="icon">
												<Save class="h-4 w-4" />
											</Button>
										</div>
									</div>
								</Card.Header>
								<hr />
								<Card.Content class="flex pt-4">
									<Table.Root>
										<Table.Header>
											<Table.Row>
												<Table.Head class="xl:table.-column">Status</Table.Head>
												<Table.Head>Department</Table.Head>
												<Table.Head class="hidden sm:table-cell"
													>Reason for Incompleteness</Table.Head
												>
												<Table.Head class="xl:table.-column text-right">Completed</Table.Head>
											</Table.Row>
										</Table.Header>
										<!-- 4 students max (recent) -->
										<Table.Body>
											<!-- library -->
											<Table.Row>
												<Table.Cell class="xl:table.-column">
													<Badge class="font-mono text-xs" variant="destructive">INC</Badge>
												</Table.Cell>
												<Table.Cell class="flex flex-col">
													<div class="font-bold">LIBRARY</div>
													<div class="text-muted-foreground text-xs md:inline">
														Librarian's Name goes here
													</div>
												</Table.Cell>
												<Table.Cell class="hidden sm:table-cell">
													<div class="font-medium">Unreturned books</div>
												</Table.Cell>
												<Table.Cell class="text-right">--/--/----</Table.Cell>
											</Table.Row>
											<!-- alum -->
											<Table.Row>
												<Table.Cell class="xl:table.-column">
													<Badge class="bg-emerald-600 font-mono text-xs" variant="default"
														>OK!</Badge
													>
												</Table.Cell>
												<Table.Cell class="flex flex-col">
													<div class="font-bold">ALUMNI AND PLACEMENT</div>
													<div class="text-muted-foreground text-xs md:inline">
														Placement Coordinator's Name goes here
													</div>
												</Table.Cell>
												<Table.Cell class="hidden sm:table-cell"></Table.Cell>
												<Table.Cell class="text-right">11:48:24 | 9 MAY 2024</Table.Cell>
											</Table.Row>
											<!-- osas -->
											<Table.Row>
												<Table.Cell class="xl:table.-column">
													<Badge class="bg-emerald-600 font-mono text-xs" variant="default"
														>OK!</Badge
													>
												</Table.Cell>
												<Table.Cell class="flex flex-col">
													<div class="font-bold">STUDENT AFFAIRS</div>
													<div class="text-muted-foreground text-xs md:inline">
														POD's Name goes here
													</div>
												</Table.Cell>
												<Table.Cell class="hidden sm:table-cell"></Table.Cell>
												<Table.Cell class="text-right">12:01:10 | 9 MAY 2024</Table.Cell>
											</Table.Row>
											<!-- guid -->
											<Table.Row>
												<Table.Cell class="xl:table.-column">
													<Badge class="bg-emerald-600 font-mono text-xs" variant="default"
														>OK!</Badge
													>
												</Table.Cell>
												<Table.Cell class="flex flex-col">
													<div class="font-bold">GUIDANCE OFFICE</div>
													<div class="text-muted-foreground text-xs md:inline">
														Guidance Counselor's Name goes here
													</div>
												</Table.Cell>
												<Table.Cell class="hidden sm:table-cell"></Table.Cell>
												<Table.Cell class="text-right">10:37:18 | 9 MAY 2024</Table.Cell>
											</Table.Row>
											<!-- dean -->
											<Table.Row>
												<Table.Cell class="xl:table.-column">
													<Badge class="bg-emerald-600 font-mono text-xs" variant="default"
														>OK!</Badge
													>
												</Table.Cell>
												<Table.Cell class="flex flex-col">
													<div class="font-bold">DEAN'S OFFICE</div>
													<div class="text-muted-foreground text-xs md:inline">
														Dean's Name goes here
													</div>
												</Table.Cell>
												<Table.Cell class="hidden sm:table-cell"></Table.Cell>
												<Table.Cell class="text-right">10:07:18 | 9 MAY 2024</Table.Cell>
											</Table.Row>
											<!-- finc -->
											<Table.Row>
												<Table.Cell class="xl:table.-column">
													<Badge class="bg-emerald-600 font-mono text-xs" variant="default"
														>OK!</Badge
													>
												</Table.Cell>
												<Table.Cell class="flex flex-col">
													<div class="font-bold">ACCOUNTING OFFICE</div>
													<div class="text-muted-foreground text-xs md:inline">
														Finance Officer's Name goes here
													</div>
												</Table.Cell>
												<Table.Cell class="hidden sm:table-cell"></Table.Cell>
												<Table.Cell class="text-right">01:13:07 | 9 MAY 2024</Table.Cell>
											</Table.Row>
											<!-- regs -->
											<Table.Row>
												<Table.Cell class="xl:table.-column">
													<Badge class="font-mono text-xs" variant="destructive">INC</Badge>
												</Table.Cell>
												<Table.Cell class="flex flex-col">
													<div class="font-bold">REGISTRAR</div>
													<div class="text-muted-foreground text-xs md:inline">
														Registrar's Name goes here
													</div>
												</Table.Cell>
												<Table.Cell class="hidden sm:table-cell">
													<div class="font-medium">Incomplete Clearance</div>
												</Table.Cell>
												<Table.Cell class="text-right">--/--/----</Table.Cell>
											</Table.Row>
										</Table.Body>
									</Table.Root>
								</Card.Content>
								<hr />
								<Card.Header class="flex flex-col gap-2">
									<div class="flex w-full flex-row place-content-between items-center">
										<Card.Title>Student Details</Card.Title>
									</div>
								</Card.Header>
								<hr />
								<Card.Content class="grid gap-4 pt-6">
									<div class="flex flex-col items-center gap-2 lg:flex-row">
										<div class="flex w-full flex-col items-start gap-2">
											<Label for="studNum" class="text-right">Student Number</Label>
											<Input readonly="studNum" class="col-span-3" placeholder="30000031859" />
										</div>
										<div class="flex w-full flex-col items-start gap-2">
											<Label for="lastName" class="text-right">Last Name</Label>
											<Input readonly id="lastName" class="col-span-3" placeholder="Dela Cruz" />
										</div>
										<div class="flex w-full flex-col items-start gap-2">
											<Label for="firstName" class="text-right">First Name</Label>
											<Input readonly id="firstName" class="col-span-3" placeholder="Juan" />
										</div>
									</div>
									<hr />
									<div class="flex w-full flex-col items-start gap-2">
										<div class="flex w-full flex-row place-content-between items-center">
											<Label for="firstName">Clearance Status</Label>
											<Badge class="font-mono text-xs" variant="outline">STAT</Badge>
										</div>
									</div>
									<div class="grid gap-2">
										<div class="flex flex-col">
											<Label>Departments Missing</Label>
											<div class="text-muted-foreground text-xs md:inline">
												Click on an incomplete department to view details.
											</div>
										</div>
										<div class="flex w-full flex-row flex-wrap gap-1">
											<Badge class="font-mono text-xs" variant="outline">LIBR</Badge>
											<Badge class="font-mono text-xs" variant="outline">ALUM</Badge>
											<Badge class="font-mono text-xs" variant="outline">OSAS</Badge>
											<Badge class="font-mono text-xs" variant="outline">GUID</Badge>
											<Badge class="font-mono text-xs" variant="outline">DEAN</Badge>
											<Badge class="font-mono text-xs" variant="outline">FINC</Badge>
											<Badge class="font-mono text-xs" variant="outline">REGS</Badge>
										</div>
									</div>
									<div class="flex w-full flex-col items-start gap-2">
										<div class="flex w-full flex-row place-content-between items-center">
											<Label for="firstName">Reason for Incompleteness</Label>
											<Badge class="font-mono text-xs" variant="outline">DEPT</Badge>
										</div>
										<Textarea
											readonly
											id="firstName"
											class="col-span-3"
											placeholder="Balance, Finals Tuition"
										/>
									</div>
								</Card.Content>
							</Card.Root>
							<!-- details -->
						</div>
					</Card.Content>
				</Card.Root>
			</div>
		</div>
	</div>
</div>

<!-- <div class="grid h-screen place-items-center items-center lg:hidden">
	<div class="flex w-5/6 flex-col gap-4">
		<Smartphone class="h-20 w-20" />
		<p class="text-2xl font-bold">You are on a smartphone.</p>
		<p class="text-balance text-sm font-medium">
			Only the student clearance form can be viewable on a smartphone. Change to a larger device to
			access the application.
		</p>
		<Button href="/account" variant="default">Return home</Button>
		<hr />
		<p class="text-muted-foreground text-balance text-xs">STIB_DSCF | ERR_DEVICE_TOO_SMALL</p>
	</div>
</div> -->
