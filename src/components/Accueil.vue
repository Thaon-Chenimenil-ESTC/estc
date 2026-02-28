<template>
    <main class="home-page">
        <section class="hero-image" aria-label="Photo du club de tennis de table">
            <img :src="heroImage" alt="Entraînement de tennis de table au club" />
            <div class="hero-overlay">
                <h1>Club de Tennis de Table</h1>
                <p>Bienvenue au club : compétition, loisir et convivialité toute l'année.</p>
            </div>
        </section>

        <section class="content-section intro">
            <h2>Bienvenue</h2>
            <p>
                Notre club accueille les joueurs de tous niveaux, des débutants curieux aux
                pongistes confirmés. En descendant la page, les blocs de contenu viennent
                progressivement recouvrir la photo d&apos;en-tête pour une transition fluide.
            </p>
        </section>

        <section class="content-section">
            <h2>Entraînements</h2>
            <p>
                Séances encadrées, ateliers techniques, matchs à thème et créneaux libres :
                tout est pensé pour progresser à son rythme, dans une ambiance dynamique.
            </p>
        </section>

        <section class="content-section">
            <h2>Compétition &amp; Loisirs</h2>
            <p>
                Le club engage plusieurs équipes en championnat et propose aussi des soirées
                conviviales, tournois internes et animations ouvertes à tous.
            </p>
        </section>

        <section class="content-section last">
            <h2>Rejoignez-nous</h2>
            <p>
                Venez essayer une séance ! Nous serons ravis de vous accueillir et de vous
                accompagner dans votre découverte du tennis de table.
            </p>
        </section>
    </main>
</template>

<script setup lang="ts">
import heroImage from '../assets/tableau_entrainements.JPG';
</script>

<style scoped>
.home-page {
    background: #f5f7fb;
}

.hero-image {
    position: sticky;
    top: 0;
    height: 70vh;
    min-height: 420px;
    overflow: hidden;
    z-index: 0;
}

.hero-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    filter: saturate(1.1);
}

.hero-overlay {
    position: absolute;
    inset: 0;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    padding: clamp(1.5rem, 3vw, 3rem);
    color: #ffffff;
    background: linear-gradient(180deg, rgba(0, 0, 0, 0.2) 15%, rgba(0, 0, 0, 0.75) 100%);
}

.hero-overlay h1 {
    margin: 0;
    font-size: clamp(2rem, 5vw, 3.5rem);
}

.hero-overlay p {
    margin: 0.75rem 0 0;
    font-size: clamp(1rem, 2.3vw, 1.35rem);
}

.content-section {
    position: relative;
    z-index: 1;
    margin: 0 auto;
    padding: 4rem clamp(1.2rem, 3vw, 2.5rem);
    background: #ffffff;
    border-top: 1px solid #e7e9f1;
    max-width: 1100px;
}

.content-section h2 {
    margin: 0 0 1rem;
    color: #1e2a49;
    font-size: clamp(1.5rem, 3vw, 2rem);
}

.content-section p {
    margin: 0;
    color: #2f3550;
    line-height: 1.65;
    max-width: 75ch;
}

.intro {
    margin-top: -18vh;
    border-top-left-radius: 1.2rem;
    border-top-right-radius: 1.2rem;
    box-shadow: 0 -12px 35px rgba(20, 30, 70, 0.2);
}

.last {
    padding-bottom: 5rem;
}

@media (max-width: 768px) {
    .hero-image {
        height: 60vh;
        min-height: 340px;
    }

    .intro {
        margin-top: -12vh;
    }
}
</style>
