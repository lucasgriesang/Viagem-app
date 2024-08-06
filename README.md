# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh
 <!-- Foi uma aula de resumo e atualização do código de viagem 
Inicialmente foi apresentado para os alunos as Regras de Negócio
As regras a se considerar:
Estamos no Brasil, então todos os pontos para calcular distância devem partir daqui.
Temos que ter pelo menos 10 destinos pré cadastrados com suas distâncias.
Calcular a distância até o destino escolhido.
Acima de 2000 Km pega 2 voos.
Se o voo for inferior a 2 meses a partir de agora é 1500 reais (considerando ida e volta).
Se o voo for igual ou superior a 2 meses a partir de agora, paga 700 reais (considerando ida e volta).
Acima de 2000 Km cada 1 Km adicional custa 1 real a mais no total.
Cada semana de estadia custará 400 reais na estalagem padrão. Ou 700 reais na estalagem de luxo.
Cada participante adicional adiciona 25% nos custos de estalagem.
Enquanto escolhe o destino, o número de participantes, o tipo de estalagem e as datas de ida e volta, sempre aperece o subtotal imediato da compra a mostra com os critérios detalhados.
Após escolher a viagem, as datas, o número de participantes, será redirecionado para tela de pagamento e fechamento de pedido, discriminando os critérios detalhados e o total. E exibindo métodos de pagamento: pix ou cartão de crédito.



Na aula do dia 6/08/2024 tivemos uma atualização no código de viagem o professor
o código era 
// jsx

// Home.jsx
import React from 'react';

const Home = () => {
  return <div><h2>Home</h2><p>Bem-vindo ao Aplicativo de Viagens!</p></div>;
};

export default Home;

// Destinos.jsx
const Destinos = () => {
  const [destinos, setDestinos] = useState([
	{ nome: 'Paris', descricao: 'A cidade do amor.' },
	{ nome: 'Nova York', descricao: 'A cidade que nunca dorme.' },
	{ nome: 'Tóquio', descricao: 'A capital do Japão.' }
  ]);

  const adicionarDestino = (novoDestino) => {
    setDestinos([...destinos, novoDestino]);
  };
  
  return <>
	  <FormDestino adicionarDestino={adicionarDestino} />
	      {destinos.map((destino, index) => (
	        <Destino key={index} nome={destino.nome} descricao={destino.descricao} />
	      ))}
  <>;
}

// Contato.jsx
import React from 'react';

const Contato = () => {
  return <div><h2>Contato</h2><p>Entre em contato conosco.</p></div>;
};

export default Contato;

// Destino.jsx
const Destino = ({ nome, descricao }) => {
  return (
    <div className="destino">
      <h2>{nome}</h2>
      <p>{descricao}</p>
    </div>
  );
};

export default Destino;

// FormDestino.jsx
import React, { useState } from 'react';

const FormDestino = ({ adicionarDestino }) => {
  const [nome, setNome] = useState('');
  const [descricao, setDescricao] = useState('');

  const handleSubmit = (e) => {
    e.preventDefault();
    adicionarDestino({ nome, descricao });
    setNome('');
    setDescricao('');
  };

  return (
    <form onSubmit={handleSubmit}>
      <input
        type="text"
        placeholder="Nome do destino"
        value={nome}
        onChange={(e) => setNome(e.target.value)}
      />
      <input
        type="text"
        placeholder="Descrição"
        value={descricao}
        onChange={(e) => setDescricao(e.target.value)}
      />
      <button type="submit">Adicionar Destino</button>
    </form>
  );
};

export default FormDestino;

// App.jsx (modificado)
import React, { useState } from 'react';
import Header from './Header';
import Footer from './Footer';
import Destino from './Destino';
import FormDestino from './FormDestino';

function App() {
  const [paginaAtual, setPaginaAtual] = useState('Home');

  const renderPagina = () => {
	switch (paginaAtual) {
	  case 'Home':
		return <Home />;
	  case 'Destinos':
		return <Destinos />;
	  case 'Contato':
		return <Contato />;
	  default:
		return <Home />;
	}
  };


  return (
    <div className="App">
      <Header />
      
      <Footer />
    </div>
  );
}

export default App;
 Tinha alguns erros que foram corrigidos no decorrer da aula 
 -->
 