<template>
    <main class="home-page">
        <section class="hero-image" aria-label="Photo du club de tennis de table">
            <img :src="heroImage" alt="Entraînement de tennis de table au club" />
            <div class="scroll-indicator" aria-hidden="true">
                <span class="mouse-icon"></span>
                <span>Descendez pour découvrir la suite</span>
                <span class="arrow">↓</span>
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
                tout est pensé pour progresser à son rythme, dans une ambiance dynamique et conviviale.
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
import heroImage from '../assets/photo-pongistes-estc.jpg';
</script>

<style scoped>
.home-page {
    background: #31313c;
}

.hero-image {
    position: sticky;
    top: 0;
    height: clamp(380px, 75vh, 900px);
    overflow: hidden;
    z-index: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #101217;
}

.hero-image img {
    width: 100%;
    height: 100%;
    object-fit: contain;
    filter: saturate(1.05);
}

.scroll-indicator {
    position: absolute;
    left: 50%;
    bottom: clamp(1rem, 4vh, 2.5rem);
    transform: translateX(-50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.35rem;
    color: #ffffff;
    text-shadow: 0 2px 8px rgba(0, 0, 0, 0.65);
    font-weight: 600;
    text-align: center;
}

.mouse-icon {
    width: 1.35rem;
    height: 2.1rem;
    border: 2px solid #ffffff;
    border-radius: 1rem;
    position: relative;
}

.mouse-icon::after {
    content: '';
    position: absolute;
    left: 50%;
    top: 0.35rem;
    width: 0.22rem;
    height: 0.4rem;
    border-radius: 999px;
    background: #ffffff;
    transform: translateX(-50%);
    animation: wheel-move 1.4s ease-in-out infinite;
}

.arrow {
    animation: bounce 1.4s ease-in-out infinite;
    font-size: 1.25rem;
}

.content-section {
    position: relative;
    z-index: 1;
    margin: 0 auto;
    padding: 4rem clamp(1.2rem, 3vw, 2.5rem);
    background: #31313c;
    width: min(90%, 1400px);
}

.content-section h2 {
    margin: 0 0 1rem;
    color: #ffffff;
    font-size: clamp(1.5rem, 3vw, 2rem);
}

.content-section p {
    margin: 0;
    color: #ffffff;
    line-height: 1.65;
    max-width: 75ch;
}

.intro {
    margin-top: 0;
    border-top-left-radius: 1.2rem;
    border-top-right-radius: 1.2rem;
    box-shadow: 0 -12px 35px rgba(20, 30, 70, 0.2);
}

.last {
    padding-bottom: 5rem;
}

@keyframes bounce {
    0%,
    100% {
        transform: translateY(0);
    }

    50% {
        transform: translateY(6px);
    }
}

@keyframes wheel-move {
    0%,
    100% {
        opacity: 0.3;
        transform: translate(-50%, 0);
    }

    50% {
        opacity: 1;
        transform: translate(-50%, 8px);
    }
}

@media (max-width: 768px) {
    .hero-image {
        height: clamp(280px, 60vh, 520px);
    }

    .content-section {
        width: min(92%, 1280px);
    }

    .scroll-indicator {
        font-size: 0.9rem;
    }
}
</style>

