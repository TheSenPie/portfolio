<template>
    <div>
        <div class="modal-container" :class="{show: modal, hiding: hiding}" @click="hideModal()">
            <img class="modal-image" v-if="filename" :src="`./static/${filename}.jpg`" alt="">
        </div>
        <section id="about">
            <div class="container">
                <div class="row">
                    <div class="col-md-5">
                        <div class="avatar-box">
                            <img width="100%" :src="`./static/avatar.jpg`" alt="Avatar">
                        </div>
                    </div>
                    <div class="col-md-7 d-flex align-items-end justify-content-end description">
                        <p>
                            Hi, my name is Smbat. I am 18 years old.<br/><br/>I am learning at Hakob Kojoyan art school, where I am in 12 grade. If I get free time I like to spend it on painting and listening songs. I found painting a very attractive way to entertain and relax at the same time. I am big fond of music and like almost every kind of music. <br/><br/> Also, as a person who likes doing good things and social works, I am a proud member of Ayo team as a volunteer.
                        </p>
                    </div>
                </div>
            </div>
        </section>
        <section id="my-works">
            <div class="container">
                <h2>My works</h2>
                <div class="row">
                    <div
                        class="col-md-4 box d-flex align-items-center justify-content-center"
                        v-for="(img, index) in images"
                        :key="index+1"
                        @click="openModal(index+1)">
                        <div class="picture֊container">
                            <img width="100%" :src="`./static/${index + 1}.jpg`" :alt="img.name">
                            <div class="filter"></div>
                        </div>
                        <div class="text">
                            <h3 v-if="img">{{img.name}}</h3>
                            <hr/>
                            <p>{{img.materials}}</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>
</template>

<script>
    export default {
        name: 'HomePage',
        data () {
            return {
                modal: false,
                filename: null,
                hiding: false,
                images: [
                    {
                        name: 'Changing famous brand name to Armenian word',
                        materials: 'paper and markers'
                    },
                    {
                        name: 'Still life',
                        materials: 'paper and gouache'
                    },
                    {
                        name: 'Opart',
                        materials: 'paper, marker and gouache'
                    },
                    {
                        name: 'Hyper realism',
                        materials: 'papaer and gouache'
                    },
                    {
                        name: `David's nose and lips drawing`,
                        materials: 'papaer and pen'
                    },
                    {
                        name: `David's eyes drawing`,
                        materials: 'papaer and pen'
                    },
                    {
                        name: 'Hyper realism',
                        materials: 'papaer and gouache'
                    },
                    {
                        name: '4 genres /Original, pointillism, cubism, surrealism/',
                        materials: 'papaer and gouache'
                    },
                    {
                        name: 'Portrait',
                        materials: 'papaer and pen'
                    },
                    {
                        name: 'Portrait',
                        materials: 'papaer and pen'
                    },
                    {
                        name: 'Opart',
                        materials: 'papaer and gouache'
                    },
                    {
                        name: 'Portrait using four colors',
                        materials: 'papaer and gouache'
                    },
                    {
                        name: 'Portrait using five colors',
                        materials: 'papaer and gouache'
                    },
                    {
                        name: 'Portrait',
                        materials: 'papaer and pen'
                    },
                    {
                        name: 'Portrait',
                        materials: 'papaer and pen'
                    },
                    {
                        name: 'Portrait using six colors',
                        materials: 'papaer and gouache'
                    }
                ]
            }
        },
        methods: {
            openModal (filename) {
                this.filename = filename
                this.modal = true
            },
            hideModal () {
                this.hiding = true
                this.filename = null
                this.modal = false
                setTimeout(() => { this.hiding = false }, 400)
            }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped="scoped"></style>
