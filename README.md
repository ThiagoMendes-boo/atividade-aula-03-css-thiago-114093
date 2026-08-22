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