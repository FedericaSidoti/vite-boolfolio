<template>
    <div class="section">
        <div class="container">
            <div class="row">
                <div class="col-6">
                    <div class="card">
                        <img class="meme" src="/img/meme-contacts.jpg">
                        
                    </div>
                </div>
                <div class="col-6">
                    <div class="card card-no-hover">
                        <img class="img-profile" src="/img/profile.jpg">
                        <h2>Dove trovarmi? </h2>
                        <p>{{ email }}</p>
                        <p>{{ cell }}</p>
                        <p> <a :href=linkedin target="_blank">Linkedin</a> </p>
                        <p><a :href=GitHub target="_blank">GitHub</a></p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
  
<script>
    export default {
    data() {
        return {
            cell: '+39 331 4903519',
            email: 'federicasidoti21@gmail.com',
            linkedin: 'https://www.linkedin.com/in/federica-sidoti-2b81b92b0/',
            GitHub: 'https://github.com/FedericaSidoti',
            }
        },
    }
</script>
  
<style lang="scss" scoped>
    .card {
        padding: 10px; 
        p {
            margin-right: 5px; 
            margin-left: 5px;
        }
        span {
            font-weight: bold;
        }

        .meme {
            max-width: 100%; 
        }

        .img-profile{
            width: 200px; 
            border-radius: 50%; 
            border: 2px solid #F18908; 
        }
    }
    .card:hover {
        padding: 8px; 
    }

    .card-no-hover:hover {
        border: none;
    }

    .section {
        padding: 80px; 
    }
</style>