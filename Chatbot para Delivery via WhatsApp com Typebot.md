# Chatbot para Delivery via WhatsApp com Typebot

Bem-vindo à documentação do projeto de Chatbot para Delivery via WhatsApp integrado com Typebot. Este Wiki contém toda a documentação técnica e funcional do projeto.

## Índice

1. [Visão Geral](#visão-geral)
2. [Declaração do Problema e Solução](#declaração-do-problema-e-solução)
3. [Requisitos](#requisitos)
   - [Requisitos Funcionais](#requisitos-funcionais)
   - [Requisitos Não Funcionais](#requisitos-não-funcionais)
4. [Histórias de Usuário](#histórias-de-usuário)
5. [Diagrama de Atividades](#diagrama-de-atividades)
6. [Implementação](#implementação)
7. [Testes](#testes)
8. [Referências](#referências)

## Visão Geral

Este projeto implementa um chatbot para serviços de delivery via WhatsApp utilizando a plataforma Typebot. O sistema automatiza o processo de atendimento ao cliente, desde o recebimento do pedido até a confirmação da entrega, incluindo processamento de pagamentos via PIX e cartão.

O chatbot é projetado para melhorar a experiência do cliente, reduzir a carga de trabalho dos atendentes humanos e otimizar o fluxo operacional do estabelecimento de delivery.

## Declaração do Problema e Solução

### Problema

Os estabelecimentos de delivery enfrentam diversos desafios no atendimento ao cliente via WhatsApp, incluindo:

1. **Sobrecarga de atendentes humanos**: Funcionários precisam responder manualmente a múltiplas conversas simultâneas, causando atrasos e inconsistências no atendimento.

2. **Ineficiência no processo de pedidos**: O processo manual de anotação de pedidos é propenso a erros e requer confirmação constante de detalhes como endereço, itens e forma de pagamento.

3. **Dificuldade no gerenciamento de pagamentos**: Diferentes métodos de pagamento (PIX, cartão) exigem processos distintos que precisam ser explicados repetidamente aos clientes.

4. **Experiência inconsistente**: A qualidade do atendimento varia conforme o atendente, horário e volume de pedidos, prejudicando a satisfação do cliente.

5. **Falta de escalabilidade**: Em horários de pico, o modelo tradicional de atendimento não consegue escalar adequadamente, resultando em clientes não atendidos ou longos tempos de espera.

### Solução

Um chatbot integrado com Typebot para WhatsApp que automatiza o processo de atendimento de delivery, oferecendo:

1. **Atendimento automatizado 24/7**: Sistema capaz de receber e processar pedidos a qualquer momento, sem necessidade de intervenção humana para fluxos padrão.

2. **Fluxo intuitivo de pedidos**: Interface conversacional que guia o cliente por todas as etapas do pedido, desde a seleção de itens até a confirmação da entrega.

3. **Gerenciamento inteligente de pagamentos**: Processamento automático de pagamentos via PIX (gerando chaves) e orientação para pagamentos com cartão (informando que o motoboy levará a máquina).

4. **Integração com sistemas existentes**: Conexão com sistemas de gerenciamento de estoque, cozinha e entrega para atualização em tempo real.

5. **Escalabilidade imediata**: Capacidade de atender centenas de clientes simultaneamente sem degradação na qualidade do serviço.

6. **Intervenção humana quando necessário**: Transferência inteligente para atendentes humanos em casos complexos ou excepcionais.

Esta solução permitirá que estabelecimentos de delivery otimizem seus processos de atendimento, reduzam custos operacionais e melhorem significativamente a experiência do cliente, resultando em maior satisfação e fidelização.

## Requisitos

### Requisitos Funcionais

1. **Inicialização de Atendimento**
   - O sistema deve cumprimentar o cliente e apresentar as opções iniciais quando uma nova conversa for iniciada
   - O sistema deve reconhecer clientes recorrentes e oferecer acesso rápido a pedidos anteriores

2. **Cardápio e Seleção de Produtos**
   - O sistema deve apresentar o cardápio completo com categorias, itens e preços
   - O sistema deve permitir a seleção de múltiplos itens em um único pedido
   - O sistema deve permitir a personalização de itens (ex: remoção de ingredientes, ponto da carne)
   - O sistema deve calcular automaticamente o valor total do pedido

3. **Gestão de Endereço**
   - O sistema deve permitir o cadastro de novos endereços
   - O sistema deve armazenar e oferecer endereços previamente utilizados
   - O sistema deve validar se o endereço está dentro da área de entrega

4. **Processamento de Pagamento**
   - O sistema deve oferecer opções de pagamento: PIX e cartão
   - Para pagamentos via PIX, o sistema deve gerar e enviar a chave de pagamento
   - Para pagamentos via cartão, o sistema deve informar que o motoboy levará a máquina
   - O sistema deve confirmar o recebimento do pagamento via PIX antes de finalizar o pedido

5. **Confirmação e Acompanhamento**
   - O sistema deve enviar uma confirmação do pedido com resumo dos itens, valor e tempo estimado
   - O sistema deve permitir o acompanhamento do status do pedido (preparação, saída para entrega)
   - O sistema deve notificar o cliente quando o pedido estiver a caminho

6. **Suporte e Feedback**
   - O sistema deve permitir que o cliente solicite atendimento humano a qualquer momento
   - O sistema deve coletar feedback após a entrega do pedido
   - O sistema deve registrar reclamações e encaminhá-las para atendentes humanos

7. **Integração com Sistemas**
   - O sistema deve integrar-se com o sistema de gerenciamento de pedidos do estabelecimento
   - O sistema deve atualizar o status do pedido automaticamente conforme atualizações do sistema interno

### Requisitos Não Funcionais

1. **Desempenho**
   - O sistema deve responder em no máximo 2 segundos a cada interação do usuário
   - O sistema deve suportar pelo menos 500 conversas simultâneas sem degradação

2. **Disponibilidade**
   - O sistema deve estar disponível 24/7, com tempo de inatividade planejado inferior a 0,1%
   - O sistema deve ter mecanismos de recuperação automática em caso de falhas

3. **Segurança**
   - O sistema deve criptografar todos os dados sensíveis dos clientes
   - O sistema deve cumprir com a LGPD (Lei Geral de Proteção de Dados)
   - O sistema deve implementar autenticação para acesso ao painel administrativo

4. **Usabilidade**
   - O fluxo de conversa deve ser intuitivo e não exigir instruções especiais
   - As mensagens devem ser claras, concisas e em linguagem amigável
   - O sistema deve oferecer opções de botões sempre que possível para facilitar a interação

5. **Escalabilidade**
   - O sistema deve escalar horizontalmente para acomodar aumento de demanda
   - O sistema deve manter performance consistente mesmo em horários de pico

6. **Manutenibilidade**
   - O código do chatbot deve ser modular para facilitar atualizações
   - Os fluxos de conversa devem ser configuráveis sem necessidade de alteração de código

7. **Compatibilidade**
   - O sistema deve funcionar corretamente em todas as versões do WhatsApp
   - O sistema deve ser compatível com diferentes dispositivos (smartphones, tablets, desktops)

8. **Monitoramento**
   - O sistema deve registrar logs detalhados de todas as interações
   - O sistema deve fornecer métricas de desempenho e uso em tempo real

## Histórias de Usuário

### Inicialização e Identificação

**História #1: Boas-vindas ao cliente**
- **Como** cliente do serviço de delivery
- **Quero** ser cumprimentado ao iniciar uma conversa no WhatsApp
- **Para que** eu saiba que estou interagindo com o sistema correto
- **Critérios de Aceitação:**
  - O chatbot deve responder em até 2 segundos após a primeira mensagem
  - A mensagem deve incluir o nome do estabelecimento
  - Deve apresentar opções iniciais (ver cardápio, fazer pedido, falar com atendente)

**História #2: Reconhecimento de cliente recorrente**
- **Como** cliente que já realizou pedidos anteriormente
- **Quero** ser reconhecido pelo sistema
- **Para que** eu não precise informar meus dados novamente
- **Critérios de Aceitação:**
  - O sistema deve identificar o cliente pelo número de WhatsApp
  - Deve cumprimentar usando o nome do cliente
  - Deve oferecer acesso rápido ao último pedido realizado
  - Deve permitir repetir pedidos anteriores com 2 cliques

### Navegação do Cardápio

**História #3: Visualização do cardápio**
- **Como** cliente interessado em fazer um pedido
- **Quero** visualizar o cardápio completo com categorias e preços
- **Para que** eu possa escolher o que desejo pedir
- **Critérios de Aceitação:**
  - O cardápio deve ser organizado por categorias (entradas, pratos principais, bebidas)
  - Cada item deve mostrar nome, breve descrição e preço
  - Deve haver opção para ver detalhes de cada item
  - Navegação deve ser intuitiva com botões para avançar/voltar entre categorias

**História #4: Busca de itens específicos**
- **Como** cliente com preferência específica
- **Quero** buscar itens por nome ou ingrediente
- **Para que** eu encontre rapidamente o que desejo
- **Critérios de Aceitação:**
  - O sistema deve oferecer opção de busca por texto
  - Resultados devem aparecer mesmo com erros de digitação leves
  - Deve mostrar itens relacionados caso a busca exata não tenha resultados

### Montagem do Pedido

**História #5: Adição de itens ao pedido**
- **Como** cliente decidindo meu pedido
- **Quero** adicionar múltiplos itens ao meu carrinho
- **Para que** eu possa fazer um pedido completo
- **Critérios de Aceitação:**
  - Deve permitir selecionar a quantidade de cada item
  - Deve confirmar cada adição com mensagem clara
  - Deve mostrar subtotal atualizado após cada adição
  - Deve permitir continuar navegando o cardápio após adicionar um item

**História #6: Personalização de itens**
- **Como** cliente com preferências específicas
- **Quero** personalizar os itens que estou pedindo
- **Para que** o pedido atenda às minhas necessidades
- **Critérios de Aceitação:**
  - Deve oferecer opções comuns de personalização para cada item
  - Deve permitir adicionar observações em texto livre
  - Deve confirmar as personalizações antes de adicionar ao carrinho
  - Deve calcular corretamente alterações de preço baseadas nas personalizações

**História #7: Revisão do carrinho**
- **Como** cliente finalizando meu pedido
- **Quero** revisar todos os itens no meu carrinho
- **Para que** eu confirme que está tudo correto antes de prosseguir
- **Critérios de Aceitação:**
  - Deve listar todos os itens com quantidades, personalizações e preços
  - Deve mostrar o subtotal, taxa de entrega e total final
  - Deve permitir remover itens ou alterar quantidades
  - Deve oferecer opção para adicionar mais itens ou finalizar o pedido

### Informações de Entrega

**História #8: Cadastro de novo endereço**
- **Como** cliente de primeira viagem ou em novo local
- **Quero** cadastrar meu endereço de entrega
- **Para que** o pedido chegue ao local correto
- **Critérios de Aceitação:**
  - Deve solicitar informações completas (rua, número, complemento, bairro)
  - Deve validar se o endereço está na área de entrega
  - Deve confirmar o endereço antes de prosseguir
  - Deve salvar o endereço para uso futuro

**História #9: Seleção de endereço existente**
- **Como** cliente recorrente
- **Quero** selecionar um endereço já cadastrado
- **Para que** eu não precise digitar tudo novamente
- **Critérios de Aceitação:**
  - Deve mostrar lista de endereços previamente utilizados
  - Deve permitir editar um endereço existente
  - Deve confirmar o endereço selecionado
  - Deve calcular corretamente a taxa de entrega baseada no endereço

### Pagamento

**História #10: Seleção de método de pagamento**
- **Como** cliente finalizando meu pedido
- **Quero** escolher como vou pagar
- **Para que** eu use o método mais conveniente para mim
- **Critérios de Aceitação:**
  - Deve apresentar opções de PIX e cartão claramente
  - Deve explicar o processo para cada método
  - Deve permitir mudar a escolha antes de confirmar

**História #11: Pagamento via PIX**
- **Como** cliente que escolheu pagar com PIX
- **Quero** receber a chave PIX para pagamento
- **Para que** eu possa efetuar a transferência
- **Critérios de Aceitação:**
  - Deve gerar e enviar a chave PIX ou QR code
  - Deve incluir o valor exato a ser pago
  - Deve fornecer instruções claras para pagamento
  - Deve confirmar quando o pagamento for recebido

**História #12: Pagamento com cartão**
- **Como** cliente que escolheu pagar com cartão
- **Quero** ser informado sobre o processo
- **Para que** eu esteja preparado quando o entregador chegar
- **Critérios de Aceitação:**
  - Deve informar claramente que o motoboy levará a máquina
  - Deve perguntar se haverá necessidade de troco (para cartão + dinheiro)
  - Deve confirmar quais bandeiras são aceitas

### Acompanhamento

**História #13: Confirmação do pedido**
- **Como** cliente após finalizar o pedido
- **Quero** receber uma confirmação detalhada
- **Para que** eu tenha certeza que tudo foi registrado corretamente
- **Critérios de Aceitação:**
  - Deve enviar resumo com itens, endereço e forma de pagamento
  - Deve informar número do pedido para referência
  - Deve informar tempo estimado de entrega
  - Deve agradecer pela preferência

**História #14: Acompanhamento do status**
- **Como** cliente aguardando meu pedido
- **Quero** acompanhar o status da preparação e entrega
- **Para que** eu saiba quando devo esperar receber
- **Critérios de Aceitação:**
  - Deve notificar quando o pedido for aceito pela cozinha
  - Deve notificar quando o pedido estiver em preparação
  - Deve notificar quando o pedido sair para entrega
  - Deve permitir que o cliente solicite atualização de status a qualquer momento

### Suporte e Feedback

**História #15: Solicitação de atendimento humano**
- **Como** cliente com dúvidas ou problemas
- **Quero** falar com um atendente humano
- **Para que** eu resolva situações que o bot não consegue atender
- **Critérios de Aceitação:**
  - Deve oferecer opção de falar com atendente em qualquer etapa
  - Deve informar tempo estimado de espera
  - Deve transferir o histórico da conversa para o atendente
  - Deve retornar ao fluxo automatizado quando o cliente desejar

**História #16: Feedback pós-entrega**
- **Como** cliente que recebeu o pedido
- **Quero** avaliar minha experiência
- **Para que** o estabelecimento possa melhorar seus serviços
- **Critérios de Aceitação:**
  - Deve solicitar avaliação após tempo estimado de entrega
  - Deve permitir avaliação por estrelas (1-5)
  - Deve permitir comentários opcionais
  - Deve agradecer pelo feedback independente da avaliação

### Administração

**História #17: Visualização de métricas (para administrador)**
- **Como** gerente do estabelecimento
- **Quero** visualizar métricas de uso do chatbot
- **Para que** eu possa avaliar sua eficácia e identificar melhorias
- **Critérios de Aceitação:**
  - Deve mostrar número de conversas iniciadas vs. pedidos concluídos
  - Deve mostrar tempo médio de atendimento
  - Deve identificar pontos de abandono no fluxo
  - Deve mostrar avaliações médias dos clientes

**História #18: Atualização de cardápio (para administrador)**
- **Como** gerente do estabelecimento
- **Quero** atualizar itens e preços no cardápio
- **Para que** as informações estejam sempre corretas
- **Critérios de Aceitação:**
  - Deve permitir adicionar, editar e remover itens
  - Deve permitir marcar itens como indisponíveis temporariamente
  - Deve permitir criar promoções com prazo de validade
  - As alterações devem refletir imediatamente nas novas conversas

## Diagrama de Atividades

[Inserir diagrama de atividades aqui]

## Implementação

### Tecnologias Utilizadas

- **Typebot**: Plataforma principal para criação e gerenciamento do fluxo do chatbot
- **WhatsApp Business API**: Interface para comunicação via WhatsApp
- **Banco de Dados**: Para armazenamento de informações de clientes, pedidos e cardápio
- **API de Pagamentos**: Para integração com sistema de pagamentos PIX
- **Sistema de Gerenciamento de Pedidos**: Para integração com o fluxo operacional do estabelecimento

### Configuração do Typebot

[Detalhes sobre a configuração do Typebot serão adicionados aqui]

## Testes

### Estratégia de Testes

- **Testes de Unidade**: Verificação de cada bloco funcional do fluxo do chatbot
- **Testes de Integração**: Verificação da integração entre o chatbot e sistemas externos
- **Testes de Usuário**: Simulação de conversas completas para validar a experiência do usuário
- **Testes de Carga**: Verificação do comportamento do sistema sob alta demanda

### Casos de Teste

[Casos de teste detalhados serão adicionados aqui]

## Referências

- [Documentação oficial do Typebot](https://docs.typebot.io/)
- [Documentação da WhatsApp Business API](https://developers.facebook.com/docs/whatsapp)
- [Melhores práticas para chatbots de atendimento](https://www.example.com)
- [Guia de User Stories](https://agilemodeling.com/artifacts/userstory.htm)
