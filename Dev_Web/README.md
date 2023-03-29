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
- Para mais informações, consulte a [documentação de Children](https://react.dev/reference/react/Children).
- A partir deste recurso, podemos utilizar `cloneElement()` (consultar [documentação](https://react.dev/reference/react/cloneElement)).
---
## Aula 04 - 29.03.2023

### Contexto

- Usualmente, passamos as informações para os componentes filhos via props.  
- Passagem por props é uma ótima maneira de canalizar dados explicitamente por meio de sua árvore de interface do usuário para os componentes que os utilizam
- Mas isso pode tornar nosso código muito verboso e incoveniente se você tiver que passar as informações para diferentes componentes filhos.  
- O ancestral comum mais próximo pode estar muito longe dos componentes que precisam de dados, e elevar o estado tão alto pode levar a uma situação chamada “Prop drilling”.  

<div>
  <img src="./imgs/A04-img01.png" alt="A04-img01" />
</div>  

- O contexto permite que um componente pai (mesmo que distante) forneça dados para toda a árvore abaixo dele.  
- Para utilizar contexto, devemos seguir os seguintes passos:  
  1. Criar um contexto.
  1. Usar esse contexto nos componentes que precisam dos dados.  
  1. Fornecer esse contexto do componente que especifica os dados.  

### Criando um contexto

```JavaScript
import { createContext } from 'react';

const MinhaCor = createContext();

export default MinhaCor;
```

### Usando o contexto

```JavaScript
import MinhaCor from './MeuContexto';

const FuncaoB = () => {
    return (
        <MinhaCor.Consumer>
            {
                (cor) => {
                    return (
                        <div>
                            <h1 style={{backgroundColor: cor}}>Função B</h1>
                        </div>
                    );
                }
            }
        </MinhaCor.Consumer>
    );
}

export default FuncaoB;
```

#### Usando o contexto com useContext()  (mais usado)

```JavaScript
import MinhaCor from './MeuContexto';
import { useContext } from 'react';

const FuncaoD = () => {
    const cor = useContext(MinhaCor);
    return (
        <div>
            <h1 style={{backgroundColor: cor}}>Função D</h1>
        </div>
    );
}

export default FuncaoD;
```

### Fornecendo o contexto do componente pai

```JavaScript
import FuncaoB from './FuncaoB';
import MinhaCor from './MeuContexto';

const FuncaoA = () => {
    const cor = 'cyan';

    return (
        <MinhaCor.Provider value={cor}>
            <div>
                <h1 style={{backgroundColor: cor}}>Funcação A</h1>
                <FuncaoB />
            </div>
        </MinhaCor.Provider>
    );
}

export default FuncaoA;
```

### useContext()

- É um React Hook que permite que você leia e assine o contexto de seu componente.
- Chame `useContext` no nível superior do seu componente para ler e assinar o contexto.
- `SomeContext`: O contexto que você criou anteriormente com createContext. O contexto em si não contém as informações, apenas representa o tipo de informação que você pode fornecer ou ler dos componentes.