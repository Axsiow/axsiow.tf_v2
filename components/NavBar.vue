<template>
    <b-navbar>
        <template #brand>
            <b-navbar-item tag="router-link" :to="{ path: '/' }">
				<div class="buttons">
					<a class="button is-primary">
						<strong>About</strong>
					</a>
				</div>
			</b-navbar-item>
            <b-navbar-item tag="router-link" :to="{ path: '/certs' }">
				<div class="buttons">
					<a class="button is-primary">
						<strong>Certifications</strong>
					</a>
				</div>
			</b-navbar-item>
            <b-navbar-item tag="router-link" :to="{ path: '/works' }">
				<div class="buttons">
					<a class="button is-primary">
						<strong>Travaux</strong>
					</a>
				</div>
			</b-navbar-item>
        </template>
        <template #start>
			
        </template>

        <template #end>
            <b-navbar-item tag="router-link" :to="{ path: '/contact' }">
                <div class="buttons">
                    <a class="button is-light">
                        Contact
                    </a>
                </div>
            </b-navbar-item>
        </template>
    </b-navbar>
</template>
