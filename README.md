# Sistema de Rastreamento de Veículos - API

Este repositório contém uma API de rastreamento de veículos construída com **NestJS**, **MongoDB**, **Prisma**, **Google Maps API** e **Docker**. A aplicação permite calcular rotas entre locais, rastrear veículos em tempo real e gerenciar motoristas e rotas de forma escalável e eficiente.

## Tecnologias Utilizadas
- **NestJS**: Framework Node.js baseado em TypeScript, ideal para construir APIs escaláveis e de alta performance.
- **MongoDB**: Banco de dados NoSQL, utilizado para armazenar dados geoespaciais e informações dinâmicas do rastreamento.
- **Prisma ORM**: Facilitador da interação com o banco de dados MongoDB, garantindo consultas seguras e eficientes.
- **Google Maps API**: Integração com a API do Google Maps para cálculos de rotas, distância, duração e direções detalhadas.
- **Docker**: Utilizado para containerizar a aplicação, garantindo um ambiente de desenvolvimento consistente e facilitando o deploy.

## Funcionalidades
- **Cálculo e Visualização de Rota**: A API do Google Maps é utilizada para calcular rotas entre pontos, incluindo distância, duração e direções detalhadas.
- **Rastreamento em Tempo Real**: Registra pontos de localização (latitude e longitude) para monitoramento contínuo de veículos durante a rota.
- **Gerenciamento de Rotas e Motoristas**: Permite criar, atualizar e gerenciar rotas e motoristas, associando motoristas a rotas específicas e rastreando seu progresso.
- **Escalabilidade e Dockerização**: A aplicação foi desenvolvida para ser facilmente escalável e portátil, utilizando Docker para isolar e padronizar o ambiente de execução.

## Requerimentos

1. **Google Maps API**: É necessário criar uma chave de API no **Google Cloud Platform** para integrar a API do Google Maps. Para isso, siga os passos abaixo:
    - Acesse o [Google Cloud Platform](https://console.cloud.google.com/).
    - Crie um novo projeto.
    - Ative as APIs do **Places** e **Directions** do Google Maps.
    - Guarde a chave de API gerada.

2. **Docker**: A aplicação usa **Docker** para configurar o ambiente. Certifique-se de ter o **Docker** e o **Docker Compose** instalados em sua máquina.

## Como Rodar a Aplicação

### 1. Clone o Repositório

```bash
git clone https://github.com/LuigiFedele/vehicleTracking.git
cd vehicleTracking
cd nest-backend
```

### 2. Configuração
Crie o arquivo `.env` a partir do arquivo de exemplo:

```bash
cp .env.example .env
```
No arquivo .env, insira sua chave de API do Google Maps gerada no Google Cloud Platform.

### 3. Levantando os Containers com Docker
Execute o seguinte comando para subir os containers do NestJS e do MongoDB:

```bash
docker-compose up -d
```

### 4. Instalando Dependências
Entre no container do NestJS e instale as dependências:

```bash
docker-compose exec app bash
npm install
```

### 5. Rodando o Servidor
Agora, inicie o servidor de desenvolvimento:

```bash
npm run start:dev
```

### 6. Chamadas HTTP
As especificações das chamadas HTTP estão no arquivo api.http. Você pode usar a extensão REST Client do VSCode para testar as rotas e interagir com a API.

### Como Funciona
- Rota: Cada rota tem um ponto de origem e um ponto de destino, além de informações como distância, duração e as direções detalhadas, que são retornadas pela API do Google Maps.
- Motorista: Cada motorista é associado a uma rota específica e tem seus pontos de localização registrados durante o percurso. O status do motorista pode ser atualizado (iniciado, finalizado) conforme o andamento da rota.
- Rastreamento: A cada ponto registrado, a localização do veículo é salva, permitindo o monitoramento em tempo real e a análise do trajeto realizado.


### Conclusão
Esse projeto foi uma oportunidade valiosa para explorar o poder das tecnologias NestJS, MongoDB, Prisma, Google Maps API e Docker. A solução foi projetada para ser escalável, eficiente e de fácil manutenção, com foco na otimização de rotas e no rastreamento em tempo real de veículos.

