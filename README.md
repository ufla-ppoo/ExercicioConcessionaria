# Concessionária Multimarcas

Este projeto é utilizado em exercícios sobre Padrões de Projeto em disciplinas de Programação Orientada a Objetos.

## Passo 1

Este projeto representa uma concessionária de forma bem simplificada, pois a intenção é facilitar a resolução dos exercícios.
Mas, especialmente **para as perguntas reflexivas** abaixo, **considere como as classes seriam em um sistema completo, bem mais complexas e extensas, e responda pensando nisso**.

Execute o programa implementado neste projeto e teste todas as suas opções.

Estude o projeto e veja que ele possui uma superclasse chamada `Carro` e subclasses para cada modelo de carro.
Ele também possui uma classe `Concessionaria`, que é a principal classe de regra de negócio do sistema, e que
permite que o usuário compre um carro.

Em seguida, mude a marca da franquia da `Concessionaria`, alterando a chamada do seu construtor, e teste o programa novamente.

## Passo 2

No passo anterior, vimos que a classe `Concessionaria` não tem os carros de todas as categorias para a Marca VW.

Faça as alterações necessárias para que a classe `Concessionaria` consiga entregar modelos de Saveiro (Pickup da VW).
Por enquanto não trate os carros de luxo.

O que você achou das mudanças no código? Lembrando que você deve considerar um sistema completo, no qual a classe `Concessionaria` seria a principal classe de regra de negócio do sistema, e, portanto, seria bem mais complexa.

> -- escreva aqui sua resposta --

O que aconteceria se o carro popular da VW passasse a ser o UP!
Que partes do código precisariam ser alteradas?

> -- escreva aqui sua resposta --

O que aconteceria se quiséssemos agora comprar carros da Chevrolet?
Que partes do código precisariam ser alteradas?

> -- escreva aqui sua resposta --

## Passo 3

Veja que no passo anterior, nós acabamos mudando o código da classe `Concessionaria` para produzir carros diferentes.
Isso está acontecendo porque nossa classe está dependendo de classes concretas (ou seja, depende da criação de objetos de tipos específicos).

Seguindo os _Princípios de Design_ que aprendemos, o ideal é que nossas classes sejam _abertas para extensão e fechadas para modificação_.
Se nós quiséssemos tratar uma nova marca (Chevrolet, por exemplo) teríamos que fazer ainda mais modificações na classe `Concessionaria`.

Na aula teórica vimos que o **Padrão de Projeto Abstract Factory** é muito útil nessas situações.
Com ele, nós poderemos criar carros de tipos diferentes, inclusive de marcas diferentes, sem precisarmos alterar o código da classe `Concessionaria` a cada novo modelo de carro.

Faça então um diagrama de classes UML das alterações necessárias para implementar o Padrão de Projeto Abstract Factory, considerando duas fábricas concretas: VW e Fiat.

### Dica sobre o Diagrama de Classes UML

No diagrama, preocupe-se em representar apenas uma visão geral das classes e dos métodos principais necessários para demonstrar a aplicação do padrão de projeto

Para fazer o diagrama você pode optar por usar:

- um software qualquer (como o `Dia`).
- ou um algum editor online como o https://www.diagrameditor.com/
- ou ainda usar o `Mermaid` que permite fazer o diagrama aqui mesmo, diretamente no arquivo README do projeto.

Caso use um software ou um editor online, exporte a modelagem para o formato `png` e coloque o arquivo em uma pasta `doc` dentro da pasta principal do projeto.

Já para usar o `Mermaid`, instale a extensão `Markdown Preview Mermaid Support` no VS Code e altere a descrição abaixo, seguindo a sintaxe do Mermaid para Diagramas de Classes UML (veja a [documentação da sintaxe](https://mermaid.js.org/syntax/classDiagram.html)).

```mermaid
---
title: Diagrama de Classes UML (incompleto)
---
classDiagram
    App --> InterfaceUsuario
    InterfaceUsuario *-- Concessionaria
    Concessionaria --> GeradorDePlaca
    Concessionaria *-- Carro
    Concessionaria *-- Argo
    Concessionaria *-- Gol
    Concessionaria *-- Strada
    Concessionaria *-- Toro
    Carro <|-- Argo
    Carro <|-- Gol
    Carro <|-- Strada
    Carro <|-- Toro
    Concessionaria : +comprarCarro(Categoria,String)
```

## Passo 4

Faça a implementação de acordo com a modelagem do exercício anterior.
Crie as classes necessárias para tratar as marcas VW e Fiat.
Teste suas alterações.

O que aconteceria agora se o carro popular da VW passasse a ser o UP!
A classe Concessionaria precisaria ser alterada?

> -- escreva aqui sua resposta --

O que aconteceria agora se quiséssemos agora comprar carros da Chevrolet?
Quais partes do código precisariam ser alteradas?

> -- escreva aqui sua resposta --

## Passo 5

Faça agora as alterações necessárias para que nossa concessionária possa vender carros da Chevrolet.

Quais mudanças foram necessárias na classe `Concessionaria`?

> -- escreva aqui sua resposta --

## Passo 6

Veja que com a utilização do Padrão de Projeto Abstract Factory nós ganhamos a possibilidade de até mudarmos a marca da franquia _em tempo de execução_, caso necessário.

Crie então na classe `Concessionaria` a opção de mudar a marca da franquia e faça os tratamentos necessários.

Adicione uma opção de menu _Mudar Franquia_ na interface do usuário, que permite que ele mude a franquia da concessionária.
Teste seu programa comprando carros de uma franquia, e depois mude a franquia e compre novos carros.

O que achou das alterações? Tente comparar como isso seria feito com o código inicial do Passo 1.

> -- escreva aqui sua resposta --
