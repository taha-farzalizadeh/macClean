<template>
    <div class="sidebar">
        <div class="sidebar-wrapper">
            <div class="logo">
                <span>T</span>Dashboard
            </div>
            <ul class="nav">
                <div class="selector-active">
                    <div class="top"></div>
                    <div class="bottom"></div>
                </div>
                <li v-for="item,index in sidebarItems" :key="index">
                    <nuxt-link @click.native="active(index)" class="nav-link" :to="{ path:`${item.path}` }"><span>{{item.title}}</span></nuxt-link>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            sidebarItems:[
                {'title':'Link 1','path':'/'},
                {'title':'Link 2','path':'/link2'},
                {'title':'Link 3','path':'/link3'},
                {'title':'Link 4','path':'/link4'},
                {'title':'Link 5','path':'/link5'},
                {'title':'Link 6','path':'/link6'}
            ]
        }
    },
    methods: {
        active(index){
            const activaor = document.querySelector('.selector-active')
            if(index === 0){activaor.style.top='165px'}
            else if(index === 1){activaor.style.top='220px'}
            else if(index === 2){activaor.style.top='273px'}
            else if(index === 3){activaor.style.top='328px'}
            else if(index === 4){activaor.style.top='382px'}
            else if(index === 5){activaor.style.top='435px'}
        }
    },
}
</script>