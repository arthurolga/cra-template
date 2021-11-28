# Proposição Stack Frontend Khipo


## Stack principal
* React v17 - Versão atual com diversas novas features
* TypeScript - JavaScript com tipagem
* Styled Components - Componentização de estilos CSS
* Context - Gerenciamento de estados padrão do React, estilo Redux
* ESlint - Linter de JavaScript e TypeScript
* Prettier - Formatador de código e espaçamentos

**Mais informações abaixo**

## Opcionais Interessantes
* Material-UI - Biblioteca de componentes, muito famosa
* Moment - Gerenciamento de data e horário
* Jest e Enzyme - Testes. Interessante utilizar juntos
* React-snap - Otimização de Loading
* Redux Toolkit - Substituio Context para casos mais complexos. Depende muito do projeto
* Bootstrap ou Bulma - Bilioteca de componentes


### TypeScript
Traz tipagem e outras novas features para o JavaScript. Junto a um linter é possível encontrar erros no código sem nem mesmo rodar. Ajuda muito na organização do código e reutilização de funçoes, componentes e interfaces. Muito difundido em projetos de empresas grandes e muito bem aceito pela comunidade.


```Typescript
\\ Type Check
const obj = { width: 10, height: 15 };
const area = obj.width * obj.heigth;
Property 'heigth' does not exist on type '{ width: number; height: number; }'. Did you mean 'height'?


\\ Interfaces
interface User { \\ Define os campos do objeto
  name: string;
  id: number;
  gender: 'male' | 'female' | 'other'; \\ Não permite outros valores
}

function createUser(user: User) { \\ Só permite a entrada de um objeto user
  ....
}

function whatever(obj: any) { \\ Permite a entrada de qualquer tipo de argumento
  ....
}

```

### Styled Components
Traz a componentização para os estilos de CSS. Deixa o código muito mais legível e reaproveitavel. Fica mais fácil componentizar tudo que possa ser usado mais de uma vez

```Javascript
\\ Sem Styled Components
<div className="container">
  <h1 className="title">
    Meu Título
  </h1>
</div>


\\ Com Styled Components
const Container = styled.section`
  padding: 4em;
  background: papayawhip;
`;
const Title = styled.h1`
  font-size: 1.5em;
  text-align: center;
  color: palevioletred;
`;

<Container>
    <Title>
      Meu Título
    </Title>
</Container>
```

### Context
É o gerenciador de estados que vem com o React. Mais leve que o Redux e geralmente muito rápido. Para a maior parte dos projetos pode fazer mais sentido utilizá-lo ao invés de Redux para diminuir o tamanho do Bundle. https://dook.pro/blog/technology/39-redux-vs-react-context-which-one-is-the-right-winner & https://reactjs.org/docs/context.html#when-to-use-context

```Typescript
const AuthContext = createContext({});
async function Login() {
   const response = await api.post('/login', {
     email: 'example@email.com',
     password: '123456',
   });

   console.log(response);
 }


<AuthContext.Provider value={{signed: true, Login}}>
   <Main />
</AuthContext.Provider>


\\ Dentro da Main
...
function handleLogin() {
   context.Login();
}
...

```



