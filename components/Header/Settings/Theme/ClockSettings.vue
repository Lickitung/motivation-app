<template>
    <b-menu-item icon="account" label="Clock">
        <h1 class="title">
        <Clock />
        </h1>
        <h2>
            <b-field>
                <b-switch v-model="isAmPm">AM/PM</b-switch>
            </b-field>
            <div class="field">
                <b-switch v-model="isSwitchedCustom"
                    true-value="HH:MM:SS"
                    false-value="HH:MM">
                    {{ isSwitchedCustom }}
                </b-switch>
            </div>
            <b-field label="Select time">
                <b-clockpicker
                    rounded
                    placeholder="Click to select..."
                    icon="clock"
                    :hour-format="format">
                </b-clockpicker>
            </b-field>
            <b-dropdown hoverable aria-role="list">
                <button class="button is-info" slot="trigger">
                    <span>Select Color</span>
                    <b-icon icon="menu-down"></b-icon>
                </button>

                <b-dropdown-item aria-role="listitem">
                    <b-button type="is-success"></b-button>
                    <b-button type="is-danger"></b-button>
                    <b-button type="is-warning"></b-button>
                    <b-button type="is-info"></b-button>
                    <b-button type="is-link"></b-button>
                    <b-button type="is-light"></b-button>
                    <b-button type="is-dark"></b-button>
                </b-dropdown-item>
            </b-dropdown>
            <br>
        </h2>
    </b-menu-item>
</template>

<script>
import Clock from '~/components/Clock'
    export default {
        components: {
            Clock
        },
        data() {
            return {
                selectedColor: 'primary',
                colors: [
                    'primary',
                    'info',
                    'success',
                    'warning',
                    'danger',
                    'white',
                    'black',
                    'light',
                    'dark'
                ],
                isSwitchedCustom: 'HH:MM:SS'
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>