<script>

    import {store} from '../store.js'

    export default {

        data() {

            return{
                
                store,
            }
        },

        methods: {
            
        },

        components: {
            
        },

        props:{
           
        }

    }

</script>


<template>
    
    <header>

        <div class="d-flex">

            <div class="col mx-5">

                <div class="d-flex navbar_left">

                    <a class="navbar-brand text-danger fs-2 pt-2" href="#">
                        Boolflix
                    </a>
                        
                    <a class=" nav-item dropdown nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">
                        Sfoglia
                    </a>

                    <ul class="dropdown-menu">

                        <li>

                            <a class="dropdown-item" href="#">
                                Popular
                            </a>

                        </li>

                        <li>

                            <a class="dropdown-item" href="#movie">
                                Movie
                            </a>

                        </li>

                        <li>

                            <a class="dropdown-item" href="#series">
                                Serie Tv
                            </a>

                        </li>

                        <li>

                            <hr class="dropdown-divider">

                        </li>

                        <li>

                            <a class="dropdown-item" href="#">
                                Lista dei preferiti
                            </a>

                        </li>

                    </ul>
                        
                </div>

            </div>

            <div class="col">

                <div class="d-flex navbar_right">

                    <form action="" @submit.prevent="$emit('search')" class="d-flex">
        
                        <input v-model="store.searchBar" class="form-control bg-transparent text-white px-2" type="text" name="" id="" placeholder="Ricerca">
        
                        <button type="submit" class="btn btn-transparent border border-danger text-white mx-2">
                            Cerca
                        </button>
        
                    </form>

                    <span class="silent-icon">
                        <i class="fa-solid fa-bell"></i>
                    </span>

                    <a class="nav-item dropdown nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">

                        <div class="profile-icon">

                            <img src="../assets/img/account.png" alt="">
                            
                        </div>

                        <span class="ps-2">
                            G
                        </span>

                    </a>

                    <ul class="dropdown-menu">

                        <li>

                            <a class="dropdown-item" href="#">
                                Altri profili
                            </a>

                        </li>

                        <li>

                            <a class="dropdown-item" href="#">
                                Impostazioni
                            </a>

                        </li>
                        
                    </ul>

                </div>

            </div>
            
        </div>

    </header>

</template>



<style lang="scss" scoped>

    @use '../assets/scss/variables.scss' as *;

    header{

        height: 60px;
        background-color: black;
        color: white;

            .navbar_left{

                >* {
                    padding: 17px 15px;
                }
            }

            .navbar_right {

            form{
                padding: 10px 0;
                width: 50%;
            }

            .silent-icon{
                padding: 20px 20px;
            }
            .profile-icon{
                width: 30px;
                height: 30px;
                margin-left: 5px;
                padding: 15px 0;
                display: inline-block;

                img{
                    width: 100%;
                }
            }

        }
    }

</style>