<script lang="ts">
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Button, buttonVariants } from '$lib/components/ui/button/index.js';
	import * as Card from '$lib/components/ui/card/index.js';
	import * as Dialog from '$lib/components/ui/dialog/index.js';
	import * as DropdownMenu from '$lib/components/ui/dropdown-menu/index.js';
	import { Input } from '$lib/components/ui/input/index.js';
	import { Label } from '$lib/components/ui/label/index.js';
	import * as Pagination from '$lib/components/ui/pagination';
	import * as Sheet from '$lib/components/ui/sheet/index.js';
	import * as Table from '$lib/components/ui/table/index.js';
	import * as Tabs from '$lib/components/ui/tabs/index.js';
	import { Textarea } from '$lib/components/ui/textarea/index.js';

	import Activity from 'lucide-svelte/icons/activity';
	import CircleUser from 'lucide-svelte/icons/circle-user';
	import CircuitBoard from 'lucide-svelte/icons/circuit-board';
	import GraduationCap from 'lucide-svelte/icons/graduation-cap';
	import Home from 'lucide-svelte/icons/home';
	import List from 'lucide-svelte/icons/list';
	import Menu from 'lucide-svelte/icons/menu';
	import Settings from 'lucide-svelte/icons/settings';
	import Smartphone from 'lucide-svelte/icons/smartphone';
	import ThumbsDown from 'lucide-svelte/icons/thumbs-down';
	import ThumbsUp from 'lucide-svelte/icons/thumbs-up';
	import UserCheck from 'lucide-svelte/icons/user-check';
	import UserX from 'lucide-svelte/icons/user-x';
	import Users from 'lucide-svelte/icons/users';
</script>

<div class="hidden flex-row lg:flex">
	<!-- sidebar (PC) -->
	<div class="hidden h-full w-72 flex-col gap-2 border-r lg:fixed lg:flex">
		<!-- header  -->
		<div class="flex h-14 items-center border-b px-4">
			<a href="/" class="flex items-center gap-2 font-semibold">
				<GraduationCap class="h-6 w-6" />
				<span class="">STIB-DSCF</span>
			</a>
		</div>
		<!-- sidebar -->
		<div class="flex-1">
			<nav class="grid items-start gap-2 px-2 text-sm font-medium lg:px-2">
				<a
					href="/dashboard"
					class="bg-muted text-primary hover:text-primary flex items-center gap-3 rounded-lg px-3 py-2 transition-all"
				>
					<Home class="h-4 w-4" />
					Dashboard
				</a>
				<hr />
				<a
					href="/students"
					class="text-muted-foreground hover:text-primary flex items-center gap-3 rounded-lg px-3 py-2 transition-all"
				>
					<Users class="h-4 w-4" />
					Student Information
				</a>
				<hr />
				<a
					href="/system"
					class="text-muted-foreground hover:text-primary flex items-center gap-3 rounded-lg px-3 py-2 transition-all"
				>
					<CircuitBoard class="h-4 w-4" />
					Section Codes
				</a>
				<a
					href="/system"
					class="text-muted-foreground hover:text-primary flex items-center gap-3 rounded-lg px-3 py-2 transition-all"
				>
					<Settings class="h-4 w-4" />
					System Settings
				</a>
				<hr />
				<a
					href="/account"
					class="text-muted-foreground hover:text-primary flex items-center gap-3 rounded-lg px-3 py-2 transition-all"
				>
					<List class="h-4 w-4" />
					Clearance Form
					<Badge class="ml-auto flex h-6 w-6 shrink-0 items-center justify-center rounded-full">
						6
					</Badge>
				</a>
				<hr />
			</nav>
		</div>
		<!-- notice -->
		<div class="mt-auto p-2">
			<Card.Root
				data-x-chunk-name="dashboard-02-chunk-0"
				data-x-chunk-description="A card with a call to action"
			>
				<Card.Header class="p-2 pt-0 md:p-4">
					<Card.Title>Bear with us.</Card.Title>
					<Card.Description>
						This version of STIB-DSCF is still under development. Report any encountered bugs by
						clicking on the button below.
					</Card.Description>
				</Card.Header>
				<Card.Content class="p-2 pt-0 md:p-4 md:pt-0">
					<Dialog.Root>
						<Dialog.Trigger class={buttonVariants({ variant: 'default' })}
							>Report Bug</Dialog.Trigger
						>
						<Dialog.Content class="sm:max-w-[425px]">
							<Dialog.Header>
								<Dialog.Title>Report a bug</Dialog.Title>
								<Dialog.Description>
									Provide details on the bug that you encountered.
								</Dialog.Description>
							</Dialog.Header>
							<div class="grid gap-4 py-4">
								<div class="grid grid-cols-4 items-center gap-4">
									<Label for="reptName" class="text-right">Name</Label>
									<Input id="reptName" placeholder="Juan Dela Cruz" class="col-span-3" />
								</div>
								<hr />
								<Label for="details">Details</Label>
								<Textarea
									placeholder="Describe the bug you encountered and how you encountered it."
								/>
							</div>
							<Dialog.Footer>
								<Button type="submit">Send Report</Button>
							</Dialog.Footer>
						</Dialog.Content>
					</Dialog.Root>
				</Card.Content>
			</Card.Root>
		</div>
	</div>
	<!-- main space -->
	<div class="flex h-screen w-screen flex-col lg:pl-72">
		<div class="fixed flex h-14 w-full items-center gap-4 border-b bg-white px-4">
			<!-- header + sidebar + footer (mb) -->
			<Sheet.Root>
				<Sheet.Trigger asChild let:builder>
					<Button variant="outline" size="icon" class="shrink-0 md:hidden" builders={[builder]}>
						<Menu class="h-5 w-5" />
						<span class="sr-only">Toggle navigation menu</span>
					</Button>
				</Sheet.Trigger>
				<Sheet.Content side="left" class="flex flex-col">
					<nav class="grid gap-2 text-lg font-medium">
						<a href="##" class="flex items-center gap-2 text-lg font-semibold">
							<GraduationCap class="h-6 w-6" />
							<span class="sr-only">STIB-DSCF</span>
						</a>
						<a
							href="/dashboard"
							class="bg-muted hover:text-foreground mx-[-0.65rem] flex items-center gap-4 rounded-xl px-3 py-2"
						>
							<Home class="h-4 w-4" />
							Dashboard
						</a>
						<hr />
						<a
							href="/students"
							class="text-muted-foreground hover:text-foreground mx-[-0.65rem] flex items-center gap-4 rounded-xl px-3 py-2"
						>
							<Users class="h-4 w-4" />
							Student Information
						</a>
						<hr />
						<a
							href="/system"
							class="text-muted-foreground hover:text-foreground mx-[-0.65rem] flex items-center gap-4 rounded-xl px-3 py-2"
						>
							<CircuitBoard class="h-4 w-4" />
							Section Codes
						</a>
						<a
							href="/system"
							class="text-muted-foreground hover:text-foreground mx-[-0.65rem] flex items-center gap-4 rounded-xl px-3 py-2"
						>
							<Settings class="h-4 w-4" />
							System Settings
						</a>
						<hr />
						<a
							href="/account"
							class="text-muted-foreground hover:text-foreground mx-[-0.65rem] flex items-center gap-4 rounded-xl px-3 py-2"
						>
							<List class="h-4 w-4" />
							Clearance Form
						</a>
						<hr />
					</nav>
					<div class="mt-auto">
						<Card.Root>
							<Card.Header>
								<Card.Title>Bear with us.</Card.Title>
								<Card.Description>
									This version of STIB-DSCF is still under development. Report any encountered bugs
									by clicking on the button below.
								</Card.Description>
							</Card.Header>
							<Card.Content>
								<Dialog.Root>
									<Dialog.Trigger class={buttonVariants({ variant: 'default' })}
										>Report Bug</Dialog.Trigger
									>
									<Dialog.Content class="sm:max-w-[425px]">
										<Dialog.Header>
											<Dialog.Title>Report a bug</Dialog.Title>
											<Dialog.Description>
												Provide details on the bug that you encountered.
											</Dialog.Description>
										</Dialog.Header>
										<div class="grid gap-4 py-4">
											<div class="grid grid-cols-4 items-center gap-4">
												<Label for="reptName" class="text-right">Name</Label>
												<Input id="reptName" placeholder="Juan Dela Cruz" class="col-span-3" />
											</div>
											<hr />
											<Label for="details">Details</Label>
											<Textarea
												placeholder="Describe the bug you encountered and how you encountered it."
											/>
										</div>
										<Dialog.Footer>
											<Button type="submit">Send Report</Button>
										</Dialog.Footer>
									</Dialog.Content>
								</Dialog.Root>
							</Card.Content>
						</Card.Root>
					</div>
				</Sheet.Content>
			</Sheet.Root>
			<div class="flex-1 items-end lg:w-full">
				<p class="text-base font-bold">Dashboard</p>
			</div>
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
		</div>
		<!-- main -->
		<div class="grid h-screen justify-between gap-2 p-2 pt-16 lg:w-full">
			<!-- values -->
			<div class="lg:w-full">
				<Card.Root>
					<Card.Header class="flex flex-row items-center justify-between space-y-0 pb-4">
						<Card.Title class="text-xl font-bold">System Analytics</Card.Title>
						<Badge variant="outline">OVERVIEW</Badge>
					</Card.Header>
					<Card.Content>
						<div class="grid gap-2 md:grid-cols-2 lg:grid-cols-4">
							<Card.Root>
								<Card.Header class="flex flex-row items-center justify-between space-y-0 pb-2">
									<Card.Title class="text-sm font-medium">Registered Students</Card.Title>
									<Users class="text-muted-foreground h-4 w-4" />
								</Card.Header>
								<Card.Content>
									<div class="text-3xl font-bold">679</div>
									<p class="text-muted-foreground text-xs">as of 7 May 2024</p>
								</Card.Content>
							</Card.Root>
							<Card.Root>
								<Card.Header class="flex flex-row items-center justify-between space-y-0 pb-2">
									<Card.Title class="text-sm font-medium">Completed Clearances</Card.Title>
									<UserCheck class="text-muted-foreground h-4 w-4" />
								</Card.Header>
								<Card.Content>
									<div class="text-3xl font-bold">429</div>
									<p class="text-muted-foreground text-xs">as of 7 May 2024</p>
								</Card.Content>
							</Card.Root>
							<Card.Root>
								<Card.Header class="flex flex-row items-center justify-between space-y-0 pb-2">
									<Card.Title class="text-sm font-medium">Incomplete Clearances</Card.Title>
									<UserX class="text-muted-foreground h-4 w-4" />
								</Card.Header>
								<Card.Content>
									<div class="text-3xl font-bold">250</div>
									<p class="text-muted-foreground text-xs">as of 7 May 2024</p>
								</Card.Content>
							</Card.Root>
							<Card.Root>
								<Card.Header class="flex flex-row items-center justify-between space-y-0 pb-2">
									<Card.Title class="text-sm font-medium">Active Now</Card.Title>
									<Activity class="text-muted-foreground h-4 w-4" />
								</Card.Header>
								<Card.Content>
									<div class="text-3xl font-bold">376</div>
									<p class="text-muted-foreground text-xs">+87 since last hour</p>
								</Card.Content>
							</Card.Root>
						</div>
					</Card.Content>
				</Card.Root>
			</div>
			<!-- student info -->
			<div class="lg:w-full">
				<Card.Root>
					<Card.Header class="flex flex-row items-center justify-between space-y-0 pb-4">
						<Card.Title class="text-xl font-bold">Student Information</Card.Title>
						<Badge variant="outline">LIVE UPDATES</Badge>
					</Card.Header>
					<Card.Content>
						<div class="grid grid-cols-3 gap-2">
							<!-- masterlist -->
							<Card.Root class="xl:col-span-2">
								<Tabs.Root>
									<Card.Header class="flex flex-col gap-2">
										<div class="flex flex-row">
											<Card.Title>Student Masterlist</Card.Title>
											<div class="flex w-full flex-row place-content-end gap-2">
												<Input
													id="search"
													class="col-span-1"
													placeholder="Type here to search..."
												/>
												<Tabs.List class="hidden lg:flex">
													<Tabs.Trigger value="all">All</Tabs.Trigger>
													<Tabs.Trigger value="ok!">Complete</Tabs.Trigger>
													<Tabs.Trigger value="inc">Incomplete</Tabs.Trigger>
												</Tabs.List>
											</div>
										</div>
									</Card.Header>
									<hr />
									<Tabs.Content value="all">
										<Card.Content>
											<Table.Root>
												<Table.Header>
													<Table.Row>
														<Table.Head class="xl:table.-column">Status</Table.Head>
														<Table.Head>Name</Table.Head>
														<Table.Head class="hidden sm:table-cell">Year & Section</Table.Head>
														<Table.Head class="xl:table.-column text-right">Depts.</Table.Head>
													</Table.Row>
												</Table.Header>
												<!-- 4 students max (recent) -->
												<Table.Body>
													<!-- student 1 -->
													<Table.Row>
														<Table.Cell class="xl:table.-column">
															<Badge class="font-mono text-xs" variant="destructive">INC</Badge>
														</Table.Cell>
														<Table.Cell class="flex flex-col">
															<div class="font-bold">WANG MALOU</div>
															<div class="text-muted-foreground text-xs md:inline">3000019758</div>
														</Table.Cell>
														<Table.Cell class="hidden sm:table-cell">
															<div class="font-medium">SHS_ITMAWD-2B</div>
														</Table.Cell>
														<Table.Cell class="text-right">
															<Badge
																class="ml-auto flex h-6 w-6 shrink-0 items-center justify-center rounded-full"
															>
																6
															</Badge>
														</Table.Cell>
													</Table.Row>
													<!-- student 2 -->
													<Table.Row>
														<Table.Cell class="xl:table.-column">
															<Badge class="bg-green-700 font-mono text-xs" variant="default"
																>OK!</Badge
															>
														</Table.Cell>
														<Table.Cell class="flex flex-col">
															<div class="font-bold">LIM ANDY</div>
															<div class="text-muted-foreground text-xs md:inline">3000185830</div>
														</Table.Cell>
														<Table.Cell class="hidden sm:table-cell">
															<div class="font-medium">CLG_BSHM-3A</div>
														</Table.Cell>
														<Table.Cell class="text-right">
															<Badge
																variant="outline"
																class="ml-auto flex h-6 w-6 shrink-0 items-center justify-center rounded-full"
															>
																0
															</Badge>
														</Table.Cell>
													</Table.Row>
													<!-- student 3 -->
													<Table.Row>
														<Table.Cell class="xl:table.-column">
															<Badge class="bg-green-700 font-mono text-xs" variant="default"
																>OK!</Badge
															>
														</Table.Cell>
														<Table.Cell class="flex flex-col">
															<div class="font-bold">DIZON JHEPOY</div>
															<div class="text-muted-foreground text-xs md:inline">3000033981</div>
														</Table.Cell>
														<Table.Cell class="hidden sm:table-cell">
															<div class="font-medium">CLG_BSIT-1A</div>
														</Table.Cell>
														<Table.Cell class="text-right">
															<Badge
																variant="outline"
																class="ml-auto flex h-6 w-6 shrink-0 items-center justify-center rounded-full"
															>
																0
															</Badge>
														</Table.Cell>
													</Table.Row>
													<!-- student 4 -->
													<Table.Row>
														<Table.Cell class="xl:table.-column">
															<Badge class="bg-green-700 font-mono text-xs" variant="default"
																>OK!</Badge
															>
														</Table.Cell>
														<Table.Cell class="flex flex-col">
															<div class="font-bold">DANQUIT JONATHAN</div>
															<div class="text-muted-foreground text-xs md:inline">3000185830</div>
														</Table.Cell>
														<Table.Cell class="hidden sm:table-cell">
															<div class="font-medium">CLG_BSHM-3A</div>
														</Table.Cell>
														<Table.Cell class="text-right">
															<Badge
																variant="outline"
																class="ml-auto flex h-6 w-6 shrink-0 items-center justify-center rounded-full"
															>
																0
															</Badge>
														</Table.Cell>
													</Table.Row>
													<!-- student 5 -->
													<Table.Row>
														<Table.Cell class="xl:table.-column">
															<Badge class="bg-green-700 font-mono text-xs" variant="default"
																>OK!</Badge
															>
														</Table.Cell>
														<Table.Cell class="flex flex-col">
															<div class="font-bold">XIAO LIZ ZEN</div>
															<div class="text-muted-foreground text-xs md:inline">3000185830</div>
														</Table.Cell>
														<Table.Cell class="hidden sm:table-cell">
															<div class="font-medium">CLG_BSHM-3A</div>
														</Table.Cell>
														<Table.Cell class="text-right">
															<Badge
																variant="outline"
																class="ml-auto flex h-6 w-6 shrink-0 items-center justify-center rounded-full"
															>
																0
															</Badge>
														</Table.Cell>
													</Table.Row>
												</Table.Body>
											</Table.Root>
											<hr />
											<br />
											<div class="hidden flex-row place-items-center lg:flex">
												<Pagination.Root count={1000} perPage={4} let:pages let:currentPage>
													<Pagination.Content>
														<Pagination.Item>
															<Pagination.PrevButton />
														</Pagination.Item>
														{#each pages as page (page.key)}
															{#if page.type === 'ellipsis'}
																<Pagination.Item>
																	<Pagination.Ellipsis />
																</Pagination.Item>
															{:else}
																<Pagination.Item isVisible={currentPage == page.value}>
																	<Pagination.Link {page} isActive={currentPage == page.value}>
																		{page.value}
																	</Pagination.Link>
																</Pagination.Item>
															{/if}
														{/each}
														<Pagination.Item>
															<Pagination.NextButton />
														</Pagination.Item>
													</Pagination.Content>
												</Pagination.Root>
											</div>
											<div class="flex flex-row lg:hidden">
												<div class="text-muted-foreground text-xs">
													On mobile, only the last four (4) students with updates show up.
												</div>
											</div>
										</Card.Content>
									</Tabs.Content>
									<Tabs.Content value="ok!">
										<Card.Content>
											<Table.Root>
												<Table.Header>
													<Table.Row>
														<Table.Head class="xl:table.-column">Status</Table.Head>
														<Table.Head>Name</Table.Head>
														<Table.Head class="hidden sm:table-cell">Year & Section</Table.Head>
														<Table.Head class="xl:table.-column text-right">Depts.</Table.Head>
													</Table.Row>
												</Table.Header>
												<!-- 4 students max (recent) -->
												<Table.Body>
													<!-- student 2 -->
													<Table.Row>
														<Table.Cell class="xl:table.-column">
															<Badge class="bg-green-700 font-mono text-xs" variant="default"
																>OK!</Badge
															>
														</Table.Cell>
														<Table.Cell class="flex flex-col">
															<div class="font-bold">LIM ANDY</div>
															<div class="text-muted-foreground text-xs md:inline">3000185830</div>
														</Table.Cell>
														<Table.Cell class="hidden sm:table-cell">
															<div class="font-medium">CLG_BSHM-3A</div>
														</Table.Cell>
														<Table.Cell class="text-right">
															<Badge
																variant="outline"
																class="ml-auto flex h-6 w-6 shrink-0 items-center justify-center rounded-full"
															>
																0
															</Badge>
														</Table.Cell>
													</Table.Row>
													<!-- student 3 -->
													<Table.Row>
														<Table.Cell class="xl:table.-column">
															<Badge class="bg-green-700 font-mono text-xs" variant="default"
																>OK!</Badge
															>
														</Table.Cell>
														<Table.Cell class="flex flex-col">
															<div class="font-bold">DIZON JHEPOY</div>
															<div class="text-muted-foreground text-xs md:inline">3000033981</div>
														</Table.Cell>
														<Table.Cell class="hidden sm:table-cell">
															<div class="font-medium">CLG_BSIT-1A</div>
														</Table.Cell>
														<Table.Cell class="text-right">
															<Badge
																variant="outline"
																class="ml-auto flex h-6 w-6 shrink-0 items-center justify-center rounded-full"
															>
																0
															</Badge>
														</Table.Cell>
													</Table.Row>
													<!-- student 4 -->
													<Table.Row>
														<Table.Cell class="xl:table.-column">
															<Badge class="bg-green-700 font-mono text-xs" variant="default"
																>OK!</Badge
															>
														</Table.Cell>
														<Table.Cell class="flex flex-col">
															<div class="font-bold">DANQIT JONATHAN</div>
															<div class="text-muted-foreground text-xs md:inline">3000185830</div>
														</Table.Cell>
														<Table.Cell class="hidden sm:table-cell">
															<div class="font-medium">CLG_BSHM-3A</div>
														</Table.Cell>
														<Table.Cell class="text-right">
															<Badge
																variant="outline"
																class="ml-auto flex h-6 w-6 shrink-0 items-center justify-center rounded-full"
															>
																0
															</Badge>
														</Table.Cell>
													</Table.Row>
													<!-- student 5 -->
													<Table.Row>
														<Table.Cell class="xl:table.-column">
															<Badge class="bg-green-700 font-mono text-xs" variant="default"
																>OK!</Badge
															>
														</Table.Cell>
														<Table.Cell class="flex flex-col">
															<div class="font-bold">XIAO LIZ ZEN</div>
															<div class="text-muted-foreground text-xs md:inline">3000185830</div>
														</Table.Cell>
														<Table.Cell class="hidden sm:table-cell">
															<div class="font-medium">CLG_BSHM-3A</div>
														</Table.Cell>
														<Table.Cell class="text-right">
															<Badge
																variant="outline"
																class="ml-auto flex h-6 w-6 shrink-0 items-center justify-center rounded-full"
															>
																0
															</Badge>
														</Table.Cell>
													</Table.Row>
													<!-- student 6 -->
													<Table.Row>
														<Table.Cell class="xl:table.-column">
															<Badge class="bg-green-700 font-mono text-xs" variant="default"
																>OK!</Badge
															>
														</Table.Cell>
														<Table.Cell class="flex flex-col">
															<div class="font-bold">AYER JAMAL</div>
															<div class="text-muted-foreground text-xs md:inline">3000185830</div>
														</Table.Cell>
														<Table.Cell class="hidden sm:table-cell">
															<div class="font-medium">CLG_BSHM-3A</div>
														</Table.Cell>
														<Table.Cell class="text-right">
															<Badge
																variant="outline"
																class="ml-auto flex h-6 w-6 shrink-0 items-center justify-center rounded-full"
															>
																0
															</Badge>
														</Table.Cell>
													</Table.Row>
												</Table.Body>
											</Table.Root>
											<hr />
											<br />
											<div class="hidden flex-row place-items-center lg:flex">
												<Pagination.Root count={1000} perPage={4} let:pages let:currentPage>
													<Pagination.Content>
														<Pagination.Item>
															<Pagination.PrevButton />
														</Pagination.Item>
														{#each pages as page (page.key)}
															{#if page.type === 'ellipsis'}
																<Pagination.Item>
																	<Pagination.Ellipsis />
																</Pagination.Item>
															{:else}
																<Pagination.Item isVisible={currentPage == page.value}>
																	<Pagination.Link {page} isActive={currentPage == page.value}>
																		{page.value}
																	</Pagination.Link>
																</Pagination.Item>
															{/if}
														{/each}
														<Pagination.Item>
															<Pagination.NextButton />
														</Pagination.Item>
													</Pagination.Content>
												</Pagination.Root>
											</div>
											<div class="flex flex-row lg:hidden">
												<div class="text-muted-foreground text-xs">
													On mobile, only the last four (4) students with updates show up.
												</div>
											</div>
										</Card.Content>
									</Tabs.Content>
									<Tabs.Content value="inc">
										<Card.Content>
											<Table.Root>
												<Table.Header>
													<Table.Row>
														<Table.Head class="xl:table.-column">Status</Table.Head>
														<Table.Head>Name</Table.Head>
														<Table.Head class="hidden sm:table-cell">Year & Section</Table.Head>
														<Table.Head class="xl:table.-column text-right">Depts.</Table.Head>
													</Table.Row>
												</Table.Header>
												<!-- 4 students max (recent) -->
												<Table.Body>
													<!-- student 1 -->
													<Table.Row>
														<Table.Cell class="xl:table.-column">
															<Badge class="font-mono text-xs" variant="destructive">INC</Badge>
														</Table.Cell>
														<Table.Cell class="flex flex-col">
															<div class="font-bold">WANG MALOU</div>
															<div class="text-muted-foreground text-xs md:inline">3000019758</div>
														</Table.Cell>
														<Table.Cell class="hidden sm:table-cell">
															<div class="font-medium">SHS_ITMAWD-2B</div>
														</Table.Cell>
														<Table.Cell class="text-right">
															<Badge
																class="ml-auto flex h-6 w-6 shrink-0 items-center justify-center rounded-full"
															>
																6
															</Badge>
														</Table.Cell>
													</Table.Row>
													<!-- student 1 -->
													<Table.Row>
														<Table.Cell class="xl:table.-column">
															<Badge class="font-mono text-xs" variant="destructive">INC</Badge>
														</Table.Cell>
														<Table.Cell class="flex flex-col">
															<div class="font-bold">LIM MADDIE</div>
															<div class="text-muted-foreground text-xs md:inline">3000019758</div>
														</Table.Cell>
														<Table.Cell class="hidden sm:table-cell">
															<div class="font-medium">SHS_ITMAWD-2B</div>
														</Table.Cell>
														<Table.Cell class="text-right">
															<Badge
																class="ml-auto flex h-6 w-6 shrink-0 items-center justify-center rounded-full"
															>
																4
															</Badge>
														</Table.Cell>
													</Table.Row>
													<!-- student 1 -->
													<Table.Row>
														<Table.Cell class="xl:table.-column">
															<Badge class="font-mono text-xs" variant="destructive">INC</Badge>
														</Table.Cell>
														<Table.Cell class="flex flex-col">
															<div class="font-bold">LEE CAOA</div>
															<div class="text-muted-foreground text-xs md:inline">3000019758</div>
														</Table.Cell>
														<Table.Cell class="hidden sm:table-cell">
															<div class="font-medium">SHS_ITMAWD-2B</div>
														</Table.Cell>
														<Table.Cell class="text-right">
															<Badge
																class="ml-auto flex h-6 w-6 shrink-0 items-center justify-center rounded-full"
															>
																7
															</Badge>
														</Table.Cell>
													</Table.Row>
													<!-- student 1 -->
													<Table.Row>
														<Table.Cell class="xl:table.-column">
															<Badge class="font-mono text-xs" variant="destructive">INC</Badge>
														</Table.Cell>
														<Table.Cell class="flex flex-col">
															<div class="font-bold">NOLA ARI</div>
															<div class="text-muted-foreground text-xs md:inline">3000019758</div>
														</Table.Cell>
														<Table.Cell class="hidden sm:table-cell">
															<div class="font-medium">SHS_ITMAWD-2B</div>
														</Table.Cell>
														<Table.Cell class="text-right">
															<Badge
																class="ml-auto flex h-6 w-6 shrink-0 items-center justify-center rounded-full"
															>
																1
															</Badge>
														</Table.Cell>
													</Table.Row>
													<!-- student 1 -->
													<Table.Row>
														<Table.Cell class="xl:table.-column">
															<Badge class="font-mono text-xs" variant="destructive">INC</Badge>
														</Table.Cell>
														<Table.Cell class="flex flex-col">
															<div class="font-bold">BAO XIAO LONG</div>
															<div class="text-muted-foreground text-xs md:inline">3000019758</div>
														</Table.Cell>
														<Table.Cell class="hidden sm:table-cell">
															<div class="font-medium">SHS_ITMAWD-2B</div>
														</Table.Cell>
														<Table.Cell class="text-right">
															<Badge
																class="ml-auto flex h-6 w-6 shrink-0 items-center justify-center rounded-full"
															>
																2
															</Badge>
														</Table.Cell>
													</Table.Row>
												</Table.Body>
											</Table.Root>
											<hr />
											<br />
											<div class="hidden flex-row place-items-center lg:flex">
												<Pagination.Root count={1000} perPage={4} let:pages let:currentPage>
													<Pagination.Content>
														<Pagination.Item>
															<Pagination.PrevButton />
														</Pagination.Item>
														{#each pages as page (page.key)}
															{#if page.type === 'ellipsis'}
																<Pagination.Item>
																	<Pagination.Ellipsis />
																</Pagination.Item>
															{:else}
																<Pagination.Item isVisible={currentPage == page.value}>
																	<Pagination.Link {page} isActive={currentPage == page.value}>
																		{page.value}
																	</Pagination.Link>
																</Pagination.Item>
															{/if}
														{/each}
														<Pagination.Item>
															<Pagination.NextButton />
														</Pagination.Item>
													</Pagination.Content>
												</Pagination.Root>
											</div>
											<div class="flex flex-row lg:hidden">
												<div class="text-muted-foreground text-xs">
													On mobile, only the last four (4) students with updates show up.
												</div>
											</div>
										</Card.Content>
									</Tabs.Content>
								</Tabs.Root>
							</Card.Root>
							<!-- details -->
							<Card.Root>
								<Card.Header class="flex flex-col gap-2">
									<div class="flex w-full flex-row place-content-between items-center">
										<Card.Title>Student Details</Card.Title>
										<div class="flex w-full flex-row place-content-end gap-2">
											<Button variant="outline" size="icon">
												<ThumbsUp class="h-4 w-4" />
											</Button>
										</div>
									</div>
								</Card.Header>
								<hr />
								<Card.Content class="grid gap-4 pt-6">
									<div class="flex w-full flex-col items-start gap-2">
										<Label for="studNum" class="text-right">Student Number</Label>
										<Input readonly="studNum" class="col-span-3" placeholder="30000031859" />
									</div>
									<div class="flex items-center gap-2">
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
										<Input
											readonly
											id="firstName"
											class="col-span-3"
											placeholder="Balance, Finals Tuition"
										/>
									</div>
								</Card.Content>
							</Card.Root>
						</div>
					</Card.Content>
				</Card.Root>
			</div>
		</div>
	</div>
</div>

<div class="grid h-screen place-items-center items-center lg:hidden">
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
</div>
