Análise Inicial
Clonei o repositório e inspecionei as pastas services/reader, services/writer e services/web.

Identifiquei que cada serviço possui falhas propositais (ex: erros de CORS, endpoints ausentes, falhas de conexão com Redis, Dockerfiles mal configurados).

2. Correções Realizadas
Docker Compose: Corrigi nomes de serviços e problemas de rede.

Dockerfiles: Ajustei paths, dependências e comandos para garantir que as aplicações inicializassem corretamente.

Redis: Verifiquei conexão entre writer e reader usando nc (netcat) e variáveis de ambiente.

Endpoints: Corrigi rotas ausentes ou incorretas, como /read no reader e /write no writer.

Frontend: Verifiquei se as requisições estavam sendo feitas corretamente, e corrigi erros como refresh is not defined.

3. Testes
Testei os serviços individualmente com curl (ex: curl http://localhost:8080/read).

Confirmei a escrita/leitura no Redis via POST e GET.

Acompanhei os logs via docker logs e execuções via docker exec.