<script>
export default {
    name: "Card",
    props: {
        name: String,
        brewery_type: String,
        city: String,
        state_province: String,
        country: String,
        phone: String,
        website_url: String,
        street: String
    }
}
</script>

<template>
    <section>
        <h2>{{ name }}</h2>
        <div>
            <div class="column">
                <h3>Dove siamo?</h3>
                <div>
                    {{ country }}, {{ state_province }}, {{ city }}, {{ street }}.
                </div>
                <h3>Come contattarci?</h3>
                <div>
                    Telefono : {{ phone }}
                </div>
                <h3>Sito web:</h3>
                <a :href="website_url">{{ name }}</a>
            </div>
            <div class="column">
                <h3>Un po' di storia:</h3>
                <p>
                    {{ name }} è un {{ brewery_type }} birrificio situato a {{ city }}. Lorem ipsum dolor, sit amet
                    consectetur adipisicing
                    elit. Dignissimos neque provident odio distinctio corrupti quas aperiam, maiores numquam voluptate,
                    nostrum aspernatur ea. Voluptas blanditiis ullam a accusamus, nemo facilis excepturi!
                </p>
            </div>
        </div>
    </section>
</template>

<style scoped>
section {
    padding-top: 1rem;
    background-image: url("../assets/img/sfondo.jpg");
    color: white;
}

h2 {
    text-align: center;
}

section>div {
    margin-top: 1rem;
    display: flex;
}

.column {
    width: 50%;
    padding: 1rem;
}

.column>div {
    margin-top: 0.5rem;
}

.column>h3 {
    margin-top: 1rem;
}

.column>h3:first-of-type {
    margin-top: 0;
}

a {
    margin-top: 0.5rem;
    display: inline-block;
    text-decoration: none;
    color: white;
}

.column:last-of-type>h3 {
    text-align: center;
}

.column>p {
    margin-top: 0.5rem;
}
</style>