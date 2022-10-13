<template>
    <section>
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
</template>

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