<template>
  <div>
		<div data-sidebar-container="chat" class="card chat-sidebar-container">
			<div data-sidebar="chat" class="chat-sidebar-wrap">
				<div class="border-right">
					<div
						class="pt-2 pb-2 pl-3 pr-3 d-flex align-items-center o-hidden box-shadow-1 chat-topbar"
					>
						<a data-sidebar-toggle="chat" class="link-icon d-md-none">
							<i class="icon-regular ml-0 mr-3 i-Left"></i>
						</a>
						<div class="form-group m-0 flex-grow-1">
							<input
								type="text"
								class="form-control form-control-rounded"
								id="search"
								placeholder="Search contacts"
							/>
						</div>
					</div>

					<div class="contacts-scrollable perfect-scrollbar">
						<div
							class="mt-4 pb-2 pl-3 pr-3 font-weight-bold text-muted border-bottom"
						>
							Recent
						</div>

						<div
							class="p-3 d-flex align-items-center border-bottom online contact"
						>
							<img
								:src="'/assets/images/faces/13.jpg'"
								class="avatar-sm rounded-circle mr-3"
								alt=""
							/>
							<div>
								<h6 class="m-0">William Wills</h6>
								<span class="text-muted text-small">3 Oct, 2018</span>
							</div>
						</div>

						<div
							class="mt-3 pb-2 pl-3 pr-3 font-weight-bold text-muted border-bottom"
						>
							Contacts
						</div>
						<div
							class="p-3 d-flex border-bottom align-items-center contact online"
						>
							<img
								:src="'/assets/images/faces/3.jpg'"
								alt=""
								class="avatar-sm rounded-circle mr-3"
							/>
							<h6 class="">Jhone Will</h6>
						</div>
						<div
							class="p-3 d-flex border-bottom align-items-center contact online"
						>
							<img
								:src="'/assets/images/faces/3.jpg'"
								alt=""
								class="avatar-sm rounded-circle mr-3"
							/>
							<h6 class="">Jhone Will</h6>
						</div>
						<div class="p-3 d-flex border-bottom align-items-center contact">
							<img
								:src="'/assets/images/faces/3.jpg'"
								alt=""
								class="avatar-sm rounded-circle mr-3"
							/>
							<h6 class="">Jhone Will</h6>
						</div>
					</div>
				</div>
			</div>
			<div data-sidebar-content="chat" class="chat-content-wrap">
				<div
					class="d-flex pl-3 pr-3 pt-2 pb-2 o-hidden box-shadow-1 chat-topbar"
				>
					<a data-sidebar-toggle="chat" class="link-icon d-md-none">
						<i class="icon-regular i-Right ml-0 mr-3"></i>
					</a>
					<div class="d-flex align-items-center">
						<img
							:src="'/assets/images/faces/13.jpg'"
							alt=""
							class="avatar-sm rounded-circle mr-2"
						/>
						<p class="m-0 text-title text-16 flex-grow-1">Frank Powell</p>
					</div>
				</div>

				<!-- Chat Item -->
				<myScroll :ops="ops" ref="vs">
					<!-- Item Chat Container -->
					<div class="chat-content perfect-scrollbar">
						<div v-for="(item, idx) in items" :key="idx">
							<div v-if="item.user_id == current_user_id" class="d-flex mb-4">
								<div class="message flex-grow-1">
									<div class="d-flex">
										<p class="mb-1 text-title text-16 flex-grow-1">
											{{ item.user_name }}
										</p>
										<span class="text-small text-muted"> {{ item.time }} </span>
									</div>
									<p class="m-0">
										{{ item.message }}
									</p>
								</div>
								<img
									:src="'/assets/images/faces/13.jpg'"
									alt=""
									class="avatar-sm rounded-circle ml-3"
								/>
							</div>

							<div v-else class="d-flex mb-4 user">
								<img
									:src="'/assets/images/faces/1.jpg'"
									alt=""
									class="avatar-sm rounded-circle mr-3"
								/>
								<div class="message flex-grow-1">
									<div class="d-flex">
										<p class="mb-1 text-title text-16 flex-grow-1">
											{{ item.user_name }}
										</p>
										<span class="text-small text-muted">{{ item.time }}</span>
									</div>
									<p class="m-0">{{ item.message }}.</p>
								</div>
							</div>
						</div>
					</div>
				</myScroll>
				<!-- <myScroll></myScroll> -->

				<!-- End Chat Item -->

				<!-- <div
					class="chat-content perfect-scrollbar"
					data-suppress-scroll-x="true"
				>
					
					
				</div> -->
				<div class="pl-3 pr-3 pt-3 pb-3 box-shadow-1 chat-input-area">
					<form @submit.prevent="sendMessage">
						<div class="form-group">
							<textarea
								v-model="form.message"
								class="form-control form-control-rounded"
								placeholder="Type your message"
								name="message"
								id="message"
								cols="30"
								rows="3"
							></textarea>
						</div>
						<div class="d-flex">
							<div class="flex-grow-1"></div>
							<button class="btn btn-icon btn-rounded btn-primary mr-2">
								<i class="i-Paper-Plane"></i>
							</button>
							<button
								class="btn btn-icon btn-rounded btn-outline-primary"
								type="button"
							>
								<i class="i-Paper-Plane"></i>
							</button>
						</div>
					</form>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {

}
</script>

<style>

</style>