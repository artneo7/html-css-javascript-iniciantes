<script>
  import '$lib/estilo.css';
  import img from '$lib/img.png';

  let preferencia = false;
</script>

<!-- Google Fonts -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Open+Sans&display=swap" rel="stylesheet">

<!-- HTML -->
<main>
  <div class="imagem">
    <div class="bg"></div>
    <img src="{img}" alt="Desenvolvedor Full Stack">
  </div>
  
  <div class="conteudo">
    <h1>Desenvolvedor Full Stack</h1>
    <h2>Precisa de um site ou app para o seu projeto?</h2>
    <button on:click={() => preferencia = 'escolher'} class="btn">Entre em contato</button>
    
    {#if preferencia === 'escolher'}
    <div class="preferencia">
      <p>Você prefere via e-mail ou WhatsApp?</p>
      <div class="btns">
        <button on:click={() => preferencia = 'email'} class="btn">E-mail</button>
        <button on:click={() => preferencia = 'whatsapp'} class="btn">WhatsApp</button>
      </div>
    </div>
    {/if}

    {#if preferencia === 'email'}
    <div class="resultado-email">
      <p>Combinado, aguardo seu contato via e-mail!</p>
      <a href="mailto:contato@artneo.com.br" class="btn">contato@artneo.com.br</a>
    </div>
    {/if}

    {#if preferencia === 'whatsapp'}
    <div class="resultado-whatsapp">
      <p>Combinado, aguardo seu contato via WhatsApp!</p>
      <a href="https://artneo.com.br/whatsapp" class="btn">(19) 98112-8000</a>
    </div>
    {/if}

  </div>
</main>

<footer>
  <span>© Desenvolvedor Full Stack, 2023</span>
</footer>

<!-- CSS -->
<style>
  main {
    display: grid;
    grid-template-columns: 230px 1fr;
    gap: 20px;
    align-items: start;
    padding: 40px;
  }
  .imagem {
    position: relative;
  }
  img {
    position: relative;
  }
  .bg {
    background-color: var(--destaque);
    width: 220px;
    height: 244px;
    position: absolute;
    bottom: 0;
    right: 0;
    opacity: 0;
    animation: mostrar 500ms forwards;
    animation-delay: 500ms;
  }
  .conteudo {
    margin-top: 8px;
    display: grid;
    gap: 8px;
  }
  .btn {
    display: inline-block;
    width: fit-content;
    background-color: var(--destaque);
    text-decoration: none;
    color: var(--branco);
    padding: 12px 16px;
    margin-bottom: 16px;
  }
  p {
    margin-bottom: 8px;
  }
  footer {
    background-color: #fff;
    height: 60px;
    display: flex;
    align-items: center;
    padding: 0 40px;
    font-size: calc(14 / 16 * 1rem);
    position: absolute;
    width: calc(100% - 80px);
    bottom: 0;
  }
  .preferencia,
  .resultado-email,
  .resultado-whatsapp {
    animation: mostrar 500ms;
  }

  @media(max-width: 700px) {
  main {
    grid-template-columns: 1fr;
  }
  .conteudo {
    grid-row: 1;
  }
  .imagem {
    max-width: 230px;
    margin-left: -10px;
  }
}
</style>