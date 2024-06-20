
# Guia de CSS Grid para Layouts Responsivos

Este repositório demonstra o uso de CSS Grid para criar layouts responsivos e atrativos. Aqui estão os principais pontos e exemplos:
## Estrutura do Projeto

- index.html: Página principal com a estrutura básica.

- style.css: Estilos CSS, incluindo definições de grid e formatação específica.


## Uso do CSS Grid

Definição do Grid Básico
css
```bash
  .page {
    max-width: clamp(33rem, 30rem + 60vw, 117rem);
    padding: 0 5rem;
    margin: 0 auto;
    display: grid;
    gap: 3.2rem;
}

@media (min-width: 700px) {
    .page {
        grid-template-columns: 1fr 1fr; /* Layout de duas colunas em telas maiores que 700px */
    }
}

@media (min-width: 930px) {
    .page {
        grid-template-areas:
            "A A B"
            "C C D"; /* Layout mais complexo em telas maiores que 930px */
    }

    .page > div:nth-child(1) {
        grid-area: A;
    }

    .page > div:nth-child(2) {
        grid-area: B;
    }

    .page > div:nth-child(3) {
        grid-area: C;
    }

    .page > div:nth-child(4) {
        grid-area: D;
    }
}

```


## Exemplo de Card Responsivo


```bash
 .card {
    display: grid;
    gap: 1rem;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
}

.card img {
    width: 100%;
    height: auto;
    object-fit: cover;
}

.card h2 {
    font-size: 1.5rem;
    text-align: center;
}

.card h2 span {
    display: block;
    text-align: center;
    padding: 0.5rem;
    background-color: #eee;
    border-radius: 4px;
    margin-top: 0.5rem;
}


```

## Animações e Configurações


```bash
 @keyframes topdown {
    0% {
        opacity: 0;
        transform: translateY(-15px);
    }
    100% {
        opacity: 1;
        transform: translateY(0);
    }
}

@keyframes downtop {
    0% {
        opacity: 0;
        transform: translateY(15px);
    }
    100% {
        opacity: 1;
        transform: translateY(0);
    }
}

.header {
    animation: topdown 700ms;
}

.card {
    animation: downtop 700ms 350ms backwards;
}


```

## Variáveis CSS Customizadas


```bash
:root {
    --ff-heading: 'Epilogue', sans-serif;
    --hue: 250;
    --bg-primary: hsl(var(--hue), 22%, 20%);
    --fc-primary: hsl(var(--hue), 0%, 100%);
    --fc-secondary: hsl(var(--hue), 50%, 80%);
    --fc-secodary-dark: hsl(var(--hue), 100%, 11%, 1);
    --fs-body: 1.6rem;
    --fs-heading: clamp(4rem, 1rem + 5vw, 51.6rem);
    --fs-heading-sm: clamp(3rem, 0.5rem + 3vw, 4rem);
    font-size: 62.5%;
}


```
##  Contribuição
Sinta-se à vontade para explorar e contribuir para este projeto! Clone o repositório e experimente ajustar os estilos de acordo com suas necessidades.





