<template>
	<div>
		<div class="main-header">
			<div class="logo">
				<img :src="'/assets/images/logo.png'" />
			</div>

			<div @click="toggleAction" class="menu-toggle">
				<div></div>
				<div></div>
				<div></div>
			</div>

			<div class="d-flex align-items-center">
				<!-- Mega menu -->
				<div class="dropdown mega-menu d-none d-md-block">
					<a
						href="#"
						class="btn text-muted dropdown-toggle mr-3"
						id="dropdownMegaMenuButton"
						data-toggle="dropdown"
						aria-haspopup="true"
						aria-expanded="false"
						>Mega Menu</a
					>
					<div
						class="dropdown-menu text-left"
						aria-labelledby="dropdownMenuButton"
					>
						<div class="row m-0">
							<div class="col-md-4 p-4 bg-img">
								<h2 class="title">
									Mega Menu <br />
									Sidebar
								</h2>
								<p>
									Lorem ipsum dolor sit amet consectetur, adipisicing elit.
									Asperiores natus laboriosam fugit, consequatur.
								</p>
								<p class="mb-4">
									Lorem ipsum dolor sit amet consectetur, adipisicing elit.
									Exercitationem odio amet eos dolore suscipit placeat.
								</p>
								<button class="btn btn-lg btn-rounded btn-outline-warning">
									Learn More
								</button>
							</div>
							<div class="col-md-4 p-4">
								<p
									class="text-primary text--cap border-bottom-primary d-inline-block"
								>
									Features
								</p>
								<div class="menu-icon-grid w-auto p-0">
									<a href="#"><i class="i-Shop-4"></i> Home</a>
									<a href="#"><i class="i-Library"></i> UI Kits</a>
									<a href="#"><i class="i-Drop"></i> Apps</a>
									<a href="#"
										><i class="i-File-Clipboard-File--Text"></i> Forms</a
									>
									<a href="#"><i class="i-Checked-User"></i> Sessions</a>
									<a href="#"><i class="i-Ambulance"></i> Support</a>
								</div>
							</div>
							<div class="col-md-4 p-4">
								<p
									class="text-primary text--cap border-bottom-primary d-inline-block"
								>
									Components
								</p>
								<ul class="links">
									<li><a>Accordion</a></li>
									<li><a>Alerts</a></li>
									<li><a>Buttons</a></li>
									<li><a>Badges</a></li>
									<li><a>Carousels</a></li>
									<li><a>Lists</a></li>
									<li><a>Popover</a></li>
									<li><a>Tables</a></li>
									<li><a>Datatables</a></li>
									<li><a>Modals</a></li>
									<li><a>Sliders</a></li>
									<li><a>Tabs</a></li>
								</ul>
							</div>
						</div>
					</div>
				</div>
				<!-- / Mega menu -->
				<vs-tooltip
					danger
					bottom
					not-hover
					border-thick
					v-model="activeTooltip1"
				>
					<div class="search-bar">
						<form @submit.prevent="SearchAction">
							<input v-model="userId" type="text" placeholder="Search" />
						</form>

						<i
							@click="SearchAction"
							class="search-icon text-muted i-Magnifi-Glass1"
						></i>
					</div>
					<template #tooltip> please fill the user-id </template>
				</vs-tooltip>
			</div>

			<div style="margin: auto"></div>

			<div class="header-part-right">
				<!-- Search Button for Mobile -->
				<div class="dropdown widget_dropdown search_contact_mobile">
					<i
						@click="activeDialogMobile = !activeDialogMobile"
						class="i-Magnifi-Glass1 text-muted header-icon"
						role="button"
					></i>
				</div>
				<!-- Notificaiton -->
				<div class="dropdown">
					<div
						class="badge-top-container"
						role="button"
						id="dropdownNotification"
						data-toggle="dropdown"
						aria-haspopup="true"
						aria-expanded="false"
					>
						<span class="badge badge-primary">3</span>
						<i class="i-Bell text-muted header-icon"></i>
					</div>
					<!-- Notification dropdown -->
					<div
						class="dropdown-menu dropdown-menu-right notification-dropdown rtl-ps-none"
						aria-labelledby="dropdownNotification"
						data-perfect-scrollbar
						data-suppress-scroll-x="true"
					>
						<div class="dropdown-item d-flex">
							<div class="notification-icon">
								<i class="i-Speach-Bubble-6 text-primary mr-1"></i>
							</div>
							<div class="notification-details flex-grow-1">
								<p class="m-0 d-flex align-items-center">
									<span>New message</span>
									<span class="badge badge-pill badge-primary ml-1 mr-1"
										>new</span
									>
									<span class="flex-grow-1"></span>
									<span class="text-small text-muted ml-auto">10 sec ago</span>
								</p>
								<p class="text-small text-muted m-0">
									James: Hey! are you busy?
								</p>
							</div>
						</div>
						<div class="dropdown-item d-flex">
							<div class="notification-icon">
								<i class="i-Receipt-3 text-success mr-1"></i>
							</div>
							<div class="notification-details flex-grow-1">
								<p class="m-0 d-flex align-items-center">
									<span>New order received</span>
									<span class="badge badge-pill badge-success ml-1 mr-1"
										>new</span
									>
									<span class="flex-grow-1"></span>
									<span class="text-small text-muted ml-auto">2 hours ago</span>
								</p>
								<p class="text-small text-muted m-0">1 Headphone, 3 iPhone x</p>
							</div>
						</div>
						<div class="dropdown-item d-flex">
							<div class="notification-icon">
								<i class="i-Empty-Box text-danger mr-1"></i>
							</div>
							<div class="notification-details flex-grow-1">
								<p class="m-0 d-flex align-items-center">
									<span>Product out of stock</span>
									<span class="badge badge-pill badge-danger ml-1 mr-1">3</span>
									<span class="flex-grow-1"></span>
									<span class="text-small text-muted ml-auto"
										>10 hours ago</span
									>
								</p>
								<p class="text-small text-muted m-0">
									Headphone E67, R98, XL90, Q77
								</p>
							</div>
						</div>
						<div class="dropdown-item d-flex">
							<div class="notification-icon">
								<i class="i-Data-Power text-success mr-1"></i>
							</div>
							<div class="notification-details flex-grow-1">
								<p class="m-0 d-flex align-items-center">
									<span>Server Up!</span>
									<span class="badge badge-pill badge-success ml-1 mr-1"
										>3</span
									>
									<span class="flex-grow-1"></span>
									<span class="text-small text-muted ml-auto"
										>14 hours ago</span
									>
								</p>
								<p class="text-small text-muted m-0">
									Server rebooted successfully
								</p>
							</div>
						</div>
					</div>
				</div>
				<!-- Notificaiton End -->

				<!-- User avatar dropdown -->
				<div class="dropdown">
					<div class="user col align-self-end">
						<img
							:src="'/assets/images/faces/1.jpg'"
							id="userDropdown"
							alt=""
							data-toggle="dropdown"
							aria-haspopup="true"
							aria-expanded="false"
						/>

						<div
							class="dropdown-menu dropdown-menu-right"
							aria-labelledby="userDropdown"
						>
							<div class="dropdown-header">
								<i class="i-Lock-User mr-1"></i> Timothy Carlson
							</div>
							<a class="dropdown-item">Account settings</a>
							<a class="dropdown-item">Billing history</a>
							<a @click="logout" class="dropdown-item">Sign out</a>
						</div>
					</div>
				</div>
			</div>
		</div>
		<!-- Contact details if the user_id exist -->
		<div ref="dialogWeb" class="center">
			<vs-dialog overflow-hidden v-model="activeDialog">
				<template #header>
					<h4 class="not-margin">Search Contact details = true</h4>
				</template>
				<div>
					<div class="card-body text-center">
						<vs-row class="mb-1" justify="center">
							<vs-avatar size="80" badge badge-color="danger">
								<img :src="'/assets/images/faces/16.jpg'" alt="" />
							</vs-avatar>
						</vs-row>
						<h5 style="margin-top: 5px" class="m-0">
							<a class="typo_link text-primary t-font-boldest">{{
								SearchData.name
							}}</a>
						</h5>
						<!-- <h5 class="m-0">Jassica Hike</h5> -->
						<p class="mt-0">{{ SearchData.about }}</p>
						<div class="separator-breadcrumb border-top"></div>
						<p>
							{{ SearchData.bio }}
						</p>

						<button
							v-if="SearchData.contactssss !== null"
							disabled
							class="btn btn-primary btn-rounded disable"
						>
							Already your contact
						</button>

						<button
							v-if="
								SearchData.contactssss === null &&
								SearchData.id !== this.currentUser.id
							"
							@click="addContact(SearchData.id)"
							class="btn btn-primary btn-rounded"
						>
							Add contact
						</button>

						<button
							v-if="SearchData.id == this.currentUser.id"
							class="btn btn-primary btn-rounded"
						>
							Setting My Account
						</button>
						<div class="card-socials-simple mt-4">
							<a href="">
								<i class="i-Linkedin-2"></i>
							</a>
							<a href="">
								<i class="i-Facebook-2"></i>
							</a>
							<a href="">
								<i class="i-Twitter"></i>
							</a>
						</div>
					</div>
				</div>
			</vs-dialog>
		</div>

		<div class="center">
			<!-- Use for toggle in mobile screen -->
			<vs-dialog overflow-hidden v-model="activeDialogMobile">
				<template #header>
					<h4 class="not-margin">Search Contact</h4>
				</template>
				<div class="con-form">
					<vs-input v-model="userId" placeholder="User-ID">
						<template #icon> @ </template>
					</vs-input>
				</div>
				<template #footer>
					<div class="footer-dialog">
						<vs-button @click="SearchAction" block> Search </vs-button>
					</div>
				</template>
			</vs-dialog>
		</div>
	</div>
</template>

<script>
import { mapActions, mapGetters } from "vuex";

export default {
	data() {
		return {
			activeTooltip1: false,
			active: 0,
			activeDialog: false,
			activeDialogMobile: false,
			userId: "",
			SearchData: {},
			progress: 0,
			enterHandler: true,
		};
	},
	computed: {
		// this is for controlling the responsive sidebar
		...mapGetters({ sideBarOpenStatus: "compt/getSidebarOpen" }),

		// this is for getting our current login user from store
		...mapGetters({ currentUser: "auth/getCurrentUser" }),
	},
	methods: {
		...mapActions(["compt/setSidebarOpen"]),
		...mapActions(["compt/setSidenavOpen"]),
		toggleAction() {
			// calling 2 method above for handling sidebar and
			// main layout to keep responsive
			this["compt/setSidebarOpen"]();
			this["compt/setSidenavOpen"]();
		},
		SearchDialog() {
			// to open the search form dialog
			this.enterHandler = !this.enterHandler;
			this.activeDialog = !this.activeDialog;
		},
		SearchAction() {
			this.activeDialog = false;

			// A variable to showing tooltip
			this.activeTooltip1 = false;

			// first we prevent user by clicking many times each second
			if (this.enterHandler) {
				this.enterHandler = !this.enterHandler;
				// if the search form is empty we showing the tooltip
				// by make the variable to true
				if (this.userId == "") {
					this.enterHandler = !this.enterHandler;
					this.activeTooltip1 = !this.activeTooltip1;
				} else {
					// open loading section
					const loading = this.$vs.loading({
						progress: 0,
						color: "#7d33ff",
						type: "scale",
					});
					const interval = setInterval(() => {
						if (this.progress <= 100) {
							loading.changeProgress(this.progress++);
						}
					}, 10);
					// end open loading section

					axios.get("/sanctum/csrf-cookie").then((response) => {
						axios.get(`/api/getsearch-contact/${this.userId}`).then((fun) => {
							// close loading section
							loading.close();
							clearInterval(interval);
							this.progress = 0;
							// end close loading section

							if (fun.data.data !== undefined) {
								this.SearchData = fun.data.data;
								this.SearchDialog();
							} else {
								// wee set each second is for 1 enter or 1 search action
								setTimeout(() => {
									this.enterHandler = !this.enterHandler;
								}, 1000);
								// and show notification if user not exist
								this.$toast.error("User not exist", "Oops!", {
									position: "topCenter", icon: 'i-Close', pauseOnHover: false
								});
								// this.ShowNotif(
								// 	"danger",
								// 	"oops! ",
								// 	"User not exist",
								// 	"<i class='i-Close' ></i>"
								// );
							}
						});
					});
				}
			}
		},
		ShowNotif(color, title, text, icon) {
			this.$vs.notification({
				icon: icon,
				progress: "auto",
				color: color,
				position: "top-center",
				title: title,
				text: text,
			});
		},
		logout() {
			const loading = this.$vs.loading({
				text: "GOODBYE...",
				progress: 0,
				color: "#7d33ff",
				type: "scale",
			});
			const interval = setInterval(() => {
				if (this.progress <= 100) {
					loading.changeProgress(this.progress++);
				}
			}, 15);
			axios.get("/sanctum/csrf-cookie").then((response) => {
				axios
					.post("/logout")
					.then((response) => {
						loading.close();
						clearInterval(interval);
						this.progress = 0;
						this.$router.push({ name: "login.page" });
					})
					.catch((error) => console.log(error));
			});
		},
		addContact(id) {
			console.log(id);
		},
	},
};
</script>


<style >
.not-margin {
	margin: 0px;
	font-weight: normal;
	padding: 10px;
}
.vs-input-content {
	margin: 10px 0px;
	width: calc(100%);
}
.vs-input {
	width: 100%;
}
</style>