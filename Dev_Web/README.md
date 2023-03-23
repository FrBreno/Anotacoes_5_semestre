# Dev Web - Jefferson de Carvalho Silva (jeffersoncarvalho@ufc.br)

![Dev meme](https://i.imgur.com/jVjoehc_d.webp?maxwidth=520&shape=thumb&fidelity=high)

## Aula 01 - 13.03.2023

---
## O que eu tenho que instalar? 

- NodeJS
- npm/npx

## Repositório

[GitHub - Jefferson Carvalho](https://github.com/jeffersoncarvalho/ufc_2023_1)
## SPA (Sigle Page Application)

Um SPA (aplicativo de página única) é uma implementação de aplicativo da Web que carrega apenas um único documento da Web e, em seguida, atualiza o conteúdo do corpo desse documento único por meio de APIs JavaScript, como XMLHttpRequest e Fetch, quando um conteúdo diferente deve ser exibido.

---  

## Aula 02 - 15.03.2023
---
Nessa aula foi apresentada as diferentes sintaxes de montagem de um componente (classe, função "normal", _arrow function_ e _arrow function_ simplificada) ou uma função. Além disso, foi explicada a forma de passar propriedades do componente pai para o componente filho.

---
## Aula 03 - 22.03.2023

### Exportando mais de um componente em um mesmo arquivo

- Exemplo de código:
    ```JavaScript
    const Header = () => {
        return (
            <div>
                <h1>Cabeçalho</h1>
            </div>
        );
    }

    const Body = () => {
        return (
            <div>
                <h1>Corpo</h1>
            </div>
        );
    }

    const Footer = () => {
        return (
            <div>
                <h1>Rodapé</h1>
            </div>
        );
    }

    export {Header, Body, Footer};
    ```
- Importação em outro arquivo (duas formas):
    ```JavaScript
    import { Header, Body, Footer } from './components/04Multiplo';
    
    import * as Site from './components/04Multiplo';
    ```

### Utilizando children

- Siga o exemplo abaixo:
    ```JavaScript
    <div className='App'>
      <Supermercado nome='DuPovu'>
        <Legume nome='Batata' />
        <Bebidas nome='Café' />
      </Supermercado>
    </div>
    ```

    ```JavaScript
    const Supermercado = (props) => {
        return (
            <div>
                <h1>Supermercado {props.nome}</h1>
                {props.children}
            </div>
        );
    }
    ```

### Utilizando Children

- `Children` é uma forma de manipulação e transformação do JSX que é recebido pela propriedade `children`.
- Ex.:
  ```JavaScript
    const mappedChildren = Children.map(children, child => 
        <div className="Row">
            {child}
        </div>
    );
  ```  
- A partir deste recurso, podemos utilizar `cloneElement()` (consultar documentação).
---
<!-- 
![Dev meme02](https://miro.medium.com/v2/resize:fit:559/1*nSfk7VzjCNeBwzlpuf1n1g.jpeg) -->