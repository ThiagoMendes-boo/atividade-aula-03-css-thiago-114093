# TH Cars - Atividade Aula 03 (CSS)

## Sobre o projeto

Peguei a página da TH Cars que fiz na Aula 2 e apliquei CSS pra dar uma identidade visual de verdade pra ela. Como é uma concessionária, pensei em fugir do "site genérico" e puxar pra um visual que lembra ficha técnica de carro, oficina, aquele letreiro de loja de veículo mesmo — por isso as cores escuras combinadas com o âmbar.

## Cores que usei

- Fundo geral da página: bege claro (`#eeece5`), pra não cansar a vista
- Header e footer: um "asfalto" bem escuro (`#1c1a19`)
- Âmbar (`#e5a13a`) como cor de destaque — borda do header, sublinhado dos títulos, borda da seção "Sobre" e os números da seção "Como Comprar"
- Cinza-aço (`#5a564f`) como segunda cor de destaque, nas bordas de "Como Comprar" e "Contato"
- Um branco levemente amarelado (`#fbfaf7`) no fundo das caixas internas, pra parecer papel/ficha

## Seletores que usei

- **Por tag:** `body`, `header`, `h1`, `nav ul`, `nav a`, `main`, `section`, `h2`, `p`, `footer`, `.card img`
- **Por classe:** `.card`, na seção de veículos, envolvendo a imagem e as categorias
- **Por id:** `#sobre`, `#servicos` e `#contato` — cada um é o destino de um link do menu lá em cima

## Onde entrou margin, padding e border

- **Margin:** usei entre as seções (`section`), pra elas não ficarem grudadas, e no `.card` (`margin-top`) pra separar ele do parágrafo de cima.
- **Padding:** em quase toda caixa com fundo (`header`, `#sobre`, `#servicos`, `#contato`, `.card`), pra o conteúdo não colar na borda. Também usei nos links do menu, senão a área de clique fica minúscula.
- **Border:** o header e o footer têm uma linha âmbar (`border-bottom`/`border-top`). As seções internas têm uma barra colorida do lado esquerdo (`border-left`). O `.card` tem borda completa mais uma sombra sólida que dá um efeito de "carimbado". E os chips de categoria de carro (Sedan, SUV...) também têm uma borda fininha.

## Como usei o box model

O exemplo mais claro é o `.card`: ele tem padding (espaço por dentro), border (a moldura), margin (espaço por fora) e ainda uma sombra reforçando. Coloquei o `* { box-sizing: border-box }` logo no topo do CSS pra garantir que padding e border não bagunçassem a largura que eu defini pros elementos — sem isso o layout começa a estourar quando você mexe no padding.

## Dificuldade que tive

No começo o cabeçalho ficava com o nome da loja em cima e o menu embaixo, meio esquisito e sem cara de site profissional. Resolvi transformando o `header` num flexbox (`display: flex; justify-content: space-between`), botando a logo de um lado e o menu do outro, na mesma linha — daí ficou muito mais parecido com um site de verdade. Também usei `flex-wrap: wrap` pra o menu não quebrar o layout se a tela for menor.

# TH Cars - Atividade Aula 04 (Layout e Responsividade)

## Sobre o projeto

Continuei a página da TH Cars que já tinha o CSS de identidade visual (Aula 03) e evoluí ela pra ficar responsiva, aplicando os conceitos de Flexbox, Grid, Mobile-first e Media Query vistos em aula. Mantive as cores, fontes e o estilo "ficha técnica de carro" que já tinha, só mudei a estrutura do layout.

## O que eu adicionei

### Flexbox
Já usava `display: flex` no header, mas faltava deixar as propriedades completas. Agora o `header`, o `nav ul`, o `.card ul`, os itens do `#servicos` e o `#contato ul` usam todas as propriedades pedidas: `display: flex`, `flex-direction`, `justify-content`, `align-items`, `gap` e `flex-wrap`.

### CSS Grid
Não tinha grid nenhum na página. Criei uma seção nova dentro de "Nossos Veículos" com 3 cartões de categoria (Sedan, Hatch, SUV) usando `.categorias-grid`, com `display: grid`, `grid-template-columns` e `gap`.

### Mobile-first
Reescrevi o CSS pra ele já nascer pensando em celular: o header fica com a logo em cima e o menu embaixo (`flex-direction: column`), e os cards de categoria ficam em 1 coluna só. Só depois, dentro do `@media (min-width: 768px)`, é que eu mudo pra tela maior.

### Media Query
Usei `@media (min-width: 768px)` pra:
- Virar o header de coluna pra linha (logo de um lado, menu do outro)
- Virar o menu de vertical pra horizontal
- Virar os cards de categoria de 1 coluna pra 3 colunas lado a lado

### Viewport
Adicionei a meta tag que tava faltando no `<head>`:
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
Sem ela o navegador do celular tratava a página como desktop e encolhia tudo.

### Unidades relativas
Troquei boa parte dos `px` fixos por `rem` (fontes, espaçamentos, largura do `main`), usei `%` na largura da imagem do card e `fr` nas colunas do grid.

## Outras mudanças

- Corrigi um erro de digitação: "Carros Ret" virou "Carros Hatch"
- Adicionei o `<footer>` no HTML — o CSS dele já existia da atividade anterior, só não tinha sido usado ainda

## Dificuldade que tive

A parte mais chata foi pensar mobile-first de verdade, e não só pegar o layout de desktop e diminuir. Tive que parar e imaginar primeiro como ficaria no celular (tudo empilhado, menu simples) e só depois escrever o `@media` pra "montar" o layout de desktop por cima disso.