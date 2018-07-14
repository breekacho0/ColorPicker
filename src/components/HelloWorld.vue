<style scoped>
    .item {
        position: relative;
        width: 100%;
        padding-top: 80%;
        text-align: center;
        border-radius: 5px;
    }

    .active {
        /* border: 1px solid #6200EE; */
        background-color: rgba(238,238,238, 0.5);
        
    }

    .info {
        position: absolute;
        top: 50%;
        left: 0;
        right: 0;
        bottom: 0;
        text-align: center;
        color: #fff;
        font-weight: 100;
    }

    .fade-enter-active,
    .fade-leave-active {
        transition: opacity 0.2s;
    }

    .fade-enter,
    .fade-leave-to {
        opacity: 0;
    }

    .manual-v-layout {
        display: -webkit-box;
        display: -ms-flexbox;
        display: flex;
        -webkit-box-flex: 1;
        -ms-flex: 1 1 auto;
        flex: 1 1 auto;
        -ms-flex-wrap: wrap;
        flex-wrap: wrap;
        -webkit-box-orient: horizontal;
        -webkit-box-direction: normal;
        -ms-flex-direction: row;
        flex-direction: row;
        padding-bottom: 8px !important;
        padding-top: 8px !important;
    }

    button {
        height: 100%;
        margin: 0;
    }

    img {
        width: 60px;
        height: 60px;
        border-radius: 50%;
    }
    .full-width{
        width: 100%;
        padding: 14px 0;
        margin-left: 10px;
    }
</style>

<template>
    <v-container fluid>
        <nav>
            <v-container fluid hidden-sm-and-down>
                <v-toolbar>
                    <v-layout justify-space-around fill-height>
                        <v-container style="padding:0" fill-height>
                            <v-flex fill-height xs10 offset-xs1>
                                <v-layout justify-space-around row fill-height align-center>
                                    <img src="../assets/logo.jpg">
                                    <v-btn flat v-on:click="showAll" v-bind:class="{'active': allActive}">All</v-btn>
                                    <v-btn flat v-on:click="setBlue" v-bind:class="{'active': activeColor.blue}">Blue</v-btn>
                                    <v-btn flat v-on:click="setRed" v-bind:class="{'active': activeColor.red}">Red</v-btn>
                                    <v-btn flat v-on:click="setYellow" v-bind:class="{'active': activeColor.yellow}">Yellow</v-btn>
                                    <v-btn flat v-on:click="setPink" v-bind:class="{'active': activeColor.pink}">Pink</v-btn>
                                    <v-btn flat v-on:click="setPurple" v-bind:class="{'active': activeColor.purple}">Purple</v-btn>
                                    <v-btn flat v-on:click="setOrange" v-bind:class="{'active': activeColor.orange}">Orange</v-btn>
                                </v-layout>
                            </v-flex>
                        </v-container>
                    </v-layout>
                </v-toolbar>
            </v-container>
            <v-container hidden-md-and-up>
                <v-expansion-panel popout>
                    <v-expansion-panel-content>
                        <div slot="header"><v-btn flat v-on:click="showAll"  class="full-width">All</v-btn></div>
                        <v-layout row justify-space-around wrap>
                        
                        <v-flex xs4> 
                            <v-btn flat v-on:click="setBlue" v-bind:class="{'active': activeColor.blue}" class="full-width">Blue</v-btn>
                        </v-flex>
                        <v-flex xs4> 
                            <v-btn flat v-on:click="setRed" v-bind:class="{'active': activeColor.red}" class="full-width">Red</v-btn>
                        </v-flex>
                        <v-flex xs4> 
                            <v-btn flat v-on:click="setYellow" v-bind:class="{'active': activeColor.yellow}" class="full-width">Yellow</v-btn>
                        </v-flex>
                        <v-flex xs4> 
                            <v-btn flat v-on:click="setPink" v-bind:class="{'active': activeColor.pink}" class="full-width">Pink</v-btn>
                        </v-flex>
                        <v-flex xs4> 
                            <v-btn flat v-on:click="setPurple" v-bind:class="{'active': activeColor.purple}" class="full-width">Purple</v-btn>
                        </v-flex>
                        <v-flex xs4> 
                            <v-btn flat v-on:click="setOrange" v-bind:class="{'active': activeColor.orange}" class="full-width">Orange</v-btn>
                        </v-flex>
                        </v-layout>
                    </v-expansion-panel-content>
                </v-expansion-panel>
            </v-container>
        </nav>
        <v-container>
            <!-- <v-layout align-center justify-space-around row wrap> -->
            <transition-group name="fade" tag="v-layout" class="manual-v-layout">
                <v-flex v-show="activeColor.red" xs6 md4 v-for="colour in red" :key="colour">
                    <v-container>
                        <div class="item" :style="{'background-color':colour.hex}">
                            <h4 class="info">{{colour.name}}</h4>
                        </div>
                    </v-container>
                </v-flex>

                <v-flex v-show="activeColor.blue" xs6 md4 v-for="colour in blue" :key="colour">
                    <v-container>
                        <div class="item" :style="{'background-color':colour.hex}">
                            <h4 class="info">{{colour.name}}</h4>
                        </div>
                    </v-container>
                </v-flex>

                <v-flex v-show="activeColor.yellow" xs6 md4 v-for="colour in yellow" :key="colour">
                    <v-container>
                        <div class="item" :style="{'background-color':colour.hex}">
                            <h4 class="info">{{colour.name}}</h4>
                        </div>
                    </v-container>
                </v-flex>

                <v-flex v-show="activeColor.pink" xs6 md4 v-for="colour in pink" :key="colour">
                    <v-container>
                        <div class="item" :style="{'background-color':colour.hex}">
                            <h4 class="info">{{colour.name}}</h4>
                        </div>
                    </v-container>
                </v-flex>

                <v-flex v-show="activeColor.purple" xs6 md4 v-for="colour in purple" :key="colour">
                    <v-container>
                        <div class="item" :style="{'background-color':colour.hex}">
                            <h4 class="info">{{colour.name}}</h4>
                        </div>
                    </v-container>
                </v-flex>
                <v-flex v-show="activeColor.orange" xs6 md4 v-for="colour in orange" :key="colour">
                    <v-container>
                        <div class="item" :style="{'background-color':colour.hex}">
                            <h4 class="info">{{colour.name}}</h4>
                        </div>
                    </v-container>
                </v-flex>

            </transition-group>
            <!-- </v-layout> -->
        </v-container>
    </v-container>
</template>

<script>
    export default {
        name: "HelloWorld",
        props: {
            msg: String
        },
        data() {
            return {
                blue: [{
                        name: "Темно-синий",
                        hex: "#02416d"
                    },
                    {
                        name: "Небесный голубой",
                        hex: "#78afce"
                    },
                    {
                        name: "Синий",
                        hex: "#015f9c"
                    },
                    {
                        name: "Аквамарин",
                        hex: "#95c3b8"
                    }
                ],
                red: [{
                        name: "Миланский красный",
                        hex: "#dd3940"
                    },
                    {
                        name: "Красный",
                        hex: "#e20001"
                    }
                ],
                yellow: [{
                    name: "Желтый",
                    hex: "#d6b202"
                }],
                orange: [{
                        name: "Теплая охра",
                        hex: "#db8a1f"
                    },
                    {
                        name: "Персиковый мусс",
                        hex: "#d3b18c"
                    }
                ],
                pink: [{
                        name: "Балетный розовый",
                        hex: "#ddc3c2"
                    },
                    {
                        name: "Коралловый",
                        hex: "#e77162"
                    }
                ],
                purple: [{
                    name: "Фиолетовый",
                    hex: "#6e4277"
                }],
                activeColor: {
                    blue: true,
                    red: true,
                    yellow: true,
                    orange: true,
                    pink: true,
                    purple: true
                }
            };
        },
        methods: {
            showAll() {
                this.activeColor.blue = true;
                this.activeColor.red = true;
                this.activeColor.yellow = true;
                this.activeColor.pink = true;
                this.activeColor.orange = true;
                this.activeColor.purple = true;
            },
            setBlue() {
                this.activeColor.blue = true;
                this.activeColor.red = false;
                this.activeColor.yellow = false;
                this.activeColor.pink = false;
                this.activeColor.orange = false;
                this.activeColor.purple = false;
            },
            setRed() {
                this.activeColor.blue = false;
                this.activeColor.red = true;
                this.activeColor.yellow = false;
                this.activeColor.pink = false;
                this.activeColor.orange = false;
                this.activeColor.purple = false;
            },
            setYellow() {
                this.activeColor.blue = false;
                this.activeColor.red = false;
                this.activeColor.yellow = true;
                this.activeColor.pink = false;
                this.activeColor.orange = false;
                this.activeColor.purple = false;
            },
            setOrange() {
                this.activeColor.blue = false;
                this.activeColor.red = false;
                this.activeColor.yellow = false;
                this.activeColor.pink = false;
                this.activeColor.orange = true;
                this.activeColor.purple = false;
            },
            setPink() {
                this.activeColor.blue = false;
                this.activeColor.red = false;
                this.activeColor.yellow = false;
                this.activeColor.pink = true;
                this.activeColor.orange = false;
                this.activeColor.purple = false;
            },
            setPurple() {
                this.activeColor.blue = false;
                this.activeColor.red = false;
                this.activeColor.yellow = false;
                this.activeColor.pink = false;
                this.activeColor.orange = false;
                this.activeColor.purple = true;
            }
        },
        computed: {
            allActive() {
                if (
                    this.activeColor.blue &&
                    this.activeColor.red &&
                    this.activeColor.yellow &&
                    this.activeColor.pink &&
                    this.activeColor.orange &&
                    this.activeColor.purple
                ) {
                    return true;
                } else {
                    return false;
                }
            }
        }
    };
</script>