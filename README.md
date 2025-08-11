A arquitetura do projeto é semelhante a um Gateway de Mensagens Adaptável com Alta Performance, cuja a principal função é intermediar a comunição com múltiplos webhooks (Whatsapp, Telegram, etc.) com uma API de Chatbot especialista.


O centro do sistema é a API Externa que atua como camada de segurança ou anticorrupção (Anti-Corruption Layer), onde seu Controller faz a tradução dos formatos de webhook para um modelo interno padronizado que garante flexibilidade de integração com novas plataformas.
Na API Externa há um orquestrados de serviços que centraliza o fluxo, gerencia e identifica usuários e o ciclo de vida das sessões. A estratégia é utilizar o Redis para cache de sessões e dados de usuário, assegurando baixa latência e chamadas desnecessárias.

O design pode ser observado conforme o fluxograma abaixo, em que o design feito cria a separação de responsabilidades: a API Externa gerencia a complexidade da conexão, autenticação e continuidade, bem como a persistência do usuário. A API de Chatbot tem a função o processamento da lingugem natural (PNL), manutenção e persistência do contexto da conversa, e a persistência da sessão.

A ideia foi trazer a escabilidade do projeto e tornar fácil sua manutenção. 

<img width="527" height="714" alt="image" src="https://github.com/user-attachments/assets/4153e56d-305c-4e72-98dc-da8e90d8204c" />



English Reference

The project architecture is similar to a High-Performance Adaptive Messaging Gateway, whose main function is to intermediate communication with multiple webhooks (WhatsApp, Telegram, etc.) through a specialized Chatbot API.

At the core of the system is the External API, which acts as a security or anti-corruption layer (Anti-Corruption Layer). Its Controller translates webhook formats into a standardized internal model, ensuring flexibility for integrating new platforms.
Within the External API, there is a service orchestrator that centralizes the flow, manages and identifies users, and handles the session lifecycle. The strategy is to use Redis for session and user data caching, ensuring low latency and avoiding unnecessary calls.

The design can be seen in the flowchart below, where it creates a clear separation of responsibilities: the External API handles the complexity of connection, authentication, and continuity, as well as user persistence. The Chatbot API is responsible for natural language processing (NLP), maintaining and persisting conversation context, and managing session persistence.

The idea was to bring scalability to the project and make its maintenance easier.

<img width="488" height="680" alt="image" src="https://github.com/user-attachments/assets/2c494284-7afc-4748-96b5-7ed7fce51b44" />
