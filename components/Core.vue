<template>
			<!-- SHORT PRES-->
	<div class="corePage">
		<h1 class="title is-1">Présentation rapide</h1>
		<div class="container">
			<div class="notification is-primary firstContainer">
				Étudiant en dernière année à l'<a href="http://ensimag.grenoble-inp.fr/" target="_blank">Ensimag (Grenoble INP)</a>
				<br>
				👩‍💻 Apprenti ingénieur réseau chez <a href="https://st.com/" target="_blank">STMicroelectronics.</a>
				<br>
				Top 1% <a href="https://tryhackme.com/" target="_blank">TryHackMe</a>.
			</div>
		</div>
				<!-- STUD EXP-->
		<section>
			<h1 class="title is-1">Parcours Académique</h1>
			<b-steps
				v-model="activeStep"
				:animated="isAnimated"
				:rounded="isRounded"
				:has-navigation="hasNavigation"
				:icon-prev="prevIcon"
				:icon-next="nextIcon"
				:label-position="labelPosition"
				:mobile-mode="mobileMode">
				<b-step-item step="1" label="Lycée André Argouges" :clickable="isStepsClickable">
					<h1 class="title has-text-centered">Baccalauréat Professionnel RPIP</h1>
					2018
				</b-step-item>

				<b-step-item step="2" label="EPSI Grenoble (bac+3)" :clickable="isStepsClickable" :type="{'is-success': isProfileSuccess}">
					<h1 class="title has-text-centered">Concepteur intégrateur SYSOPS/Administrateur Système Réseaux et Bases de Données</h1>
					2018 - 2021
				</b-step-item>

				<b-step-item step="3" label="EPSI Grenoble (bac+4)" :clickable="isStepsClickable">
					<h1 class="title has-text-centered">Master 1 expert en informatique et système d'information option cybersécurité et intelligence artificielle</h1>
					2021 - 2022
				</b-step-item>

				<b-step-item :step="showSocial ? '4' : '3'" label=" Grenoble INP - ENSIMAG (bac+5)" :clickable="isStepsClickable" disabled>
					<h1 class="title has-text-centered">Master 2 Réseaux Informatiques d’Entreprise (RIE)</h1>
					2022 - 2023
				</b-step-item>

				<template
					v-if="customNavigation"
					#navigation="{previous, next}">
					<b-button
						outlined
						type="is-danger"
						icon-pack="fas"
						icon-left="backward"
						:disabled="previous.disabled"
						@click.prevent="previous.action">
						Previous
					</b-button>
					<b-button
						outlined
						type="is-success"
						icon-pack="fas"
						icon-right="forward"
						:disabled="next.disabled"
						@click.prevent="next.action">
						Next
					</b-button>
				</template>
			</b-steps>
    	</section>
				<!-- PRO EXP -->
		<section>
			<h1 class="title is-1">Parcours Professionnel</h1>
			<div class="buttons ProEXP">
				<b-button
					label="Space Generation Advisory Council (Bénévolat)"
					type="is-primary"
					size="is-medium"
					@click="alertSGAC" />

				<b-button
					label="STMictroelectronics (alternance)"
					type="is-primary"
					size="is-medium"
					@click="alertSTA" />

				<b-button
					label="STMictroelectronics (stage)"
					type="is-primary"
					size="is-medium"
					@click="alertSTS" />
				
				<b-button
					label="Grenoble Alpes (bénévolat)"
					type="is-primary"
					size="is-medium"
					@click="alertPionnier" />

				<b-button
					label="Auphys Technologies (stage)"
					type="is-primary"
					size="is-medium"
					@click="alertAuphys" />
				
				<b-button
					label="Leonix Telecom (stage)"
					type="is-primary"
					size="is-medium"
					@click="alertLeonix" />

				<b-button
					label="Twitter (Bénévolat)"
					type="is-primary"
					size="is-medium"
					@click="alertTwitter" />
			</div>
		</section>
	</div>
	
</template>
				<!-- JS STUD EXP-->
<script>
export default {
    data() {
        return {
            activeStep: 0,

            showSocial: true,
            isAnimated: true,
            isRounded: true,
            isStepsClickable: true,

            hasNavigation: true,
            customNavigation: false,
            isProfileSuccess: false,

            prevIcon: 'chevron-left',
            nextIcon: 'chevron-right',
            labelPosition: 'bottom',
            mobileMode: 'minimalist'
        }
    }
}
</script>
				<!-- JS PRO EXP-->
<script>
export default {
    methods: {
        alertSGAC() {
            this.$buefy.dialog.alert({
                title: 'SGAC (bénevolat)',
                message: "<b>Septembre 2022 - présent</b><br><br>Le Space Generation Advisory Council est une organisation et un réseau mondial non gouvernemental à but non lucratif (US 501(c)3) qui vise à représenter les étudiants universitaires et les jeunes professionnels de l'espace auprès des Nations Unies, des agences spatiales, de l'industrie et du milieu universitaire.<br><br><b>Missions.</b><br>• Réflexion autour de la cybersécurité dans le domaine du spatiale à l'international<br>• co-organisation d'un hackathon",
                canCancel: 'outside',
				confirmText: 'Cool!'
            })
        },
        alertSTA() {
            this.$buefy.dialog.alert({
                title: 'STMictroelectronics (alternance)',
                message: "<b>2020 - 2023</b><br><br><b>Gestion du réseau existant.</b><br>• Mise en place de la surveillance des équipements réseaux avec Zabbix Graphana<br>• Intégration des outils Cisco Prime pour les nouvelles gammes de switch Cisco<br><br><b>Sécurisation de l'infrastructure réseau.</b><br>• Participation à la migration du réseau Facilities vers des équipements Cisco avec un objectif de sécurisation et de fiabilisation en lien avec les équipes Facilities<br>• Ajout de switchs manageables dans une zone de laboratoires pour rempalcer des équipements non surveillés et mettre en place un verrouillage NAC en lien avec les équipes du laboratoires.<br><br><b>Cybersécurité.</b><br>• Suivis de tests de pentest effectué sur l'infrastructure et participation à la remédiation de l'attaque<br>• Configuration de firewall Cisco et Palo Alto<br><br><b>Construire et manager un SI.</b><br>• Configuration de nouveaux switchs pour le réseau ST Crolles<br>• Génération de configurations pour le déploiement d'une flotte de switchs<br>• Support des équipements réseaux existants (environ 300 équipements actifs)<br><br><b>Gérer un parc informatique.</b><br>• Ajout de modules à notre outil de gestion des connexions réseaux (cabling)<br>• Utilisation configuration et développement sur la solution Cisco Prime<br><br><b>Développer les actions d'information et communication.</b><br>• Documentation des missions effectuées pour garantir leur utilisation et leur maintien futur",
                canCancel: 'outside',
				confirmText: 'Cool!'
            })
        },
        alertSTS() {
            this.$buefy.dialog.alert({
                title: 'STMictroelectronics (stage)',
                message: "<b>Février et juillet 2020</b><br><br>Développement d'outils de surveillance de réseau. Besoin d'améliorer la solution de surveillance par un outil open source d'évaluation (Zabbix) recueillir les besoins et développer une nouvelle interface web",
                canCancel: 'outside',
				confirmText: 'Cool!'
            })
        },
		alertPionnier() {
            this.$buefy.dialog.alert({
                title: 'Grenoble Alpes (bénévolat)',
                message: "<b>Septembre 2020 - présent</b><br><br>Grenoble et sa région sont intimement liées aux montagnes qui l’entourent.<br>Les Alpes ont forgé notre caractère, entre modestie et persévérance ; admiration et créativité.<br>Cet environnement particulier a fait naître en chacun de nous un esprit pionnier, à l’origine des valeurs que nous défendons aujourd’hui : le progrès, le bien-vivre, le courage et l’ouverture.",
                canCancel: 'outside',
				confirmText: 'Cool!'
            })
        },
		alertAuphys() {
            this.$buefy.dialog.alert({
                title: 'Auphys Technologies (stage)',
                message: "<b>Juillet et aout 2020</b><br><br>Stage de 8 semaines en tant que Web Développeur et Designer, avec notament la création de Auphys Works.",
                canCancel: 'outside',
				confirmText: 'Cool!'
            })
        },
		alertLeonix() {
            this.$buefy.dialog.alert({
                title: 'Leonix Telecom (stage)',
                message: "<b>Mai et juin 2019</b><br><br>Stage de 6 semaines dans le pôle ingénierie en collaboration avec les équipes réseaux de l'opérateur Leonix Telecom.",
                canCancel: 'outside',
				confirmText: 'Cool!'
            })
        },
		alertTwitter() {
            this.$buefy.dialog.alert({
                title: 'Twitter (Bénévolat) • 2016 - 2017',
                message: "Traducteur de l'anglais vers le français sur la plateforme de traduction de Twitter.",
                canCancel: 'outside',
				confirmText: 'Cool!'
            })
        }
    }
}
</script>

<style>
.b-steps {
	text-align: center;
}

.is-1 {
	text-align: center;
	margin-top: 100px;
	padding-bottom: 25px;
}

.corePage{
	min-height: 50vh;
	display: flex;
	flex-direction: column;
	justify-content: space-around;
}

.ProEXP{
	margin-bottom: 100px;
	display: flex;
	flex-direction: row;
	justify-content: center;
}

</style>