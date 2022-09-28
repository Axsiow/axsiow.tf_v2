<template>
    <b-navbar>
        <template #brand>
            <b-navbar-item tag="router-link" :to="{ path: '/' }">
				<div class="buttons">
					<a class="button is-primary">
						<strong>Home</strong>
					</a>
				</div>
			</b-navbar-item>
        </template>
        <template #start>
			
        </template>

        <template #end>
            <b-navbar-item tag="div">
                <div class="buttons">
                	<a class="button is-primary">
                        <strong>About</strong>
                    </a>
                    <a class="button is-light">
                        Contacts
                    </a>
                </div>
            </b-navbar-item>
        </template>
    </b-navbar>
</template>
