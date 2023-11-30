<script>
export default {
    name: "Card"
}
</script>

<template>
    <section>
        <h2>Name</h2>
        <div>
            <div class="column">
                <h3>Dove siamo?</h3>
                <div>
                    Country, State province, City, Street
                </div>
                <h3>Come contattarci?</h3>
                <div>
                    Telefono : Phone
                </div>
                <h3>Sito web</h3>
                <a href="Website URL">Name</a>
            </div>
            <div class="column">
                <h3>Un po' di storia</h3>
                <p>
                    Name è un Brewery type birrificio situato a City. Lorem ipsum dolor, sit amet consectetur adipisicing
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