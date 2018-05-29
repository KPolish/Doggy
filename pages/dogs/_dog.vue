<template>
    <section class="section">
        <article class="hero">
            <div class="hero-body">
                <div class="container">
                    <h1 class="title">저는 {{dogName}} 입니다.</h1>
                    <h2 class="subtitle">그러합니다.</h2>
                </div>
            </div>
        </article>

        {{dogName}}
    </section>
</template>
<script>
    export default {
        asyncData({params}) {
            return{
                dogName: params.dog
            };
        }
    }
</script>