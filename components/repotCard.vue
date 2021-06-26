<template>
    <div class="rep-card flex-column align-items-center d-flex justify-content-center">
        <div class="header-border d-flex mt-3">
            <div class="card-icon" :class="[color]">
                <fa class="icons" :icon="['fas', `${this.icon}`]" />
            </div>
        </div>
        <div class="card-title pt-3">
            {{title}}
        </div>
        
    </div>
</template>

<script>
export default {
    props:['icon' , 'color' ,'title'],
}
</script>

<style lang="scss" scoped>

</style>