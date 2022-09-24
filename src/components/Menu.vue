<template>
    <div class="menu" :class="{ 'small-menu': smallMenu }">
        <div class="logo">
            <img src="../assets/img/logo.png" alt="">
        </div>
        <h4>Menu</h4>
        <MenuItem v-for="(item, index) in menuTree" :key="index" :data="item.children" :label="item.label"
            :icon="item.icon" :depth="0" :smallMenu="smallMenu" />
        <i @click="smallMenu = !smallMenu" class="material-icons">menu</i>
        <div class="navbar ">
            <h4>Profil</h4>
        </div>
        <MenuItem v-for="(item, index) in menuProfil" :key="index" :data="item.children" :label="item.label"
            :icon="item.icon" :depth="0" :smallMenu="smallMenu" />
        <i @click="smallMenu = !smallMenu" class="material-icons">menu</i>
    </div>
</template>
  
<script >
import MenuItem from './MenuItem.vue';


export default {

    name: 'recursive-menu',
    data: () => ({

        smallMenu: false,
        menuTree: [
            {

                label: "Overview",
                icon: "grid_view",

            }

            ,
            {

                label: "Kegiatan",
                icon: "computer",

            }

            ,
            {
                label: "Funding",
                icon: "paid"
            },
            {

                label: "Pengguna",
                icon: "group",
                children: [{
                    label: "Peserta UMKM",
                }

                    ,
                {
                    label: "Investor"
                }

                    ,
                {
                    label: "Admin"
                }

                ]
            },
            {
                label: "Pesan",
                icon: "chat"
            }

        ],
        menuProfil: [
            {

                label: "Overview",
                icon: "grid_view",

            }

            ,
            {

                label: "Kegiatan",
                icon: "computer",

            }



        ]

    }),
    components: {
        MenuItem
    }
}
</script>
  
<style lang="scss" scoped>
.menu {


    position: flex;
    height: 100vh;
    width: 240px;
    left: 0;
    top: 0;
    border-right: 1px solid #ececec;
    transition: all .3s ease;
    overflow: auto;

    .navbar {
        margin-top: 400px;
    }

    h4 {
        font-family: 'Manrope';
        font-size: 16px;
        margin-top: 24px;

    }


    i {
        position: fixed;
        left: 250px;
        font-size: 20px;
        top: 15px;
        user-select: none;
        cursor: pointer;
        transition: all .3s ease;
    }

    &.small-menu {
        overflow: inherit;
        width: 60px;
        padding-top: 50px;

        i {
            left: 20px;
        }
    }
}
</style>