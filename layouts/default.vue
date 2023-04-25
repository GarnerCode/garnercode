<template>
    <div>
        <Navbar></Navbar>
        <main>
            <Nuxt />
        </main>
        <Footer></Footer>
    </div>
</template>

<style lang="scss">
  @import '@/static/assets/styles.scss';
  @import url('https://fonts.googleapis.com/css2?family=Roboto&family=Roboto+Condensed&display=swap');
  :root {
    --color-black: #2D333C;
    --color-white: #fff;
    --color-primary: #00C95A;
    --color-secondary: #0768FB;

    --font-family-primary: 'Roboto', sans-serif;
    --font-family-secondary: 'Roboto Condensed', sans-serif;

    --image-box-shadow: -10px -10px 0px var(--color-primary), 10px 10px 0px var(--color-black);

    --border-radius: 8px;
  }
  @media screen and (min-width: 0px) {
    * {
      font-family: var(--font-family-primary);
    }
    h1, h2, h3 {
        margin: 0;
        font-family: var(--font-family-secondary);
    }
    h1 {
        font-size: 8rem;
    }
    h2 {
        font-size: 6rem;
    }
    h3 {
        font-size: 3rem;
    }
    p {
        font-size: 16px;
    }
    .button {
        text-decoration: none;
        background: none;
        color: var(--color-primary);
        border: 1px solid var(--color-primary);
        font-size: 16px;
        display: block;
        width: 100%;
        text-align: center;
        padding: 1.6rem 0;
        border-radius: var(--border-radius);
        transition: all 0.1s ease;
        &:hover {
            background-color: var(--color-primary);
            color: var(--color-white);
        }
    }
    .text-highlight {
        color: var(--color-primary) !important;
    }
    .py {
        padding-top: 10rem;
        padding-bottom: 10rem;
    }
    .px {
        padding-left: 4rem;
        padding-right: 4rem;
    }
    .section-header-top {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
    }
    .header-bar {
        background-color: var(--color-primary);
        display: block;
        height: 1px;
        width: 28rem;
    }
  }
</style>