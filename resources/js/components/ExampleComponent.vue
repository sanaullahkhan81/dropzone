<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">Upload File</div>
                    <div class="card-body">
                        <vue-dropzone ref="myVueDropzone" id="dropzone" :options="dropzoneOptions"></vue-dropzone>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

    import vue2Dropzone from 'vue2-dropzone'
    //import stljs from 'stljs'
    import 'vue2-dropzone/dist/vue2Dropzone.min.css'


    export default {
        components: {
            vueDropzone: vue2Dropzone
        },
        data: function () {
            return {
                dropzoneOptions: {
                    url: '/formSubmit',
                    headers: {
                        "X-CSRF-TOKEN": document.head.querySelector("[name=csrf-token]").content
                    }
                }
            }
        },
        mounted() {
            console.log('Component mounted.')
        }
    }
</script>
