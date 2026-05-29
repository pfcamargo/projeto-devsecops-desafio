1. Passo 1: Checkout do Código
O que faz: Baixa uma cópia do código do repositório para dentro da máquina virtual temporária do GitHub Actions.

Importância: É o primeiro passo necessário para que as ferramentas de segurança consigam "ler" os nossos arquivos.

2. Passo 2: Build de Validação
O que faz: Executa um comando simples para listar e verificar se a pasta de código-fonte (src/) está estruturada corretamente.

Importância: Garante que os arquivos básicos do site estão no lugar certo antes de gastar tempo rodando os testes avançados.

3. Passo 3: Secrets Scanning (Gitleaks)
O que faz: Vasculha todo o histórico do projeto procurando por senhas, chaves de API ou tokens que os desenvolvedores possam ter esquecido expostos.

Importância: Evita o risco de Hardcoded Passwords (senhas gravadas direto no texto). Deixar uma senha exposta no GitHub é como deixar a chave da empresa na fechadura pelo lado de fora. O Gitleaks gera um relatório (gitleaks-report.sarif) detalhando qualquer suspeita encontrada.

4. Passo 4: SAST - Análise Estática (Semgrep)
O que faz: Faz uma varredura profunda no texto do código-fonte (sem precisar ligar o sistema), procurando por práticas de programação inseguras ou brechas de lógica.

Importância: Funciona como um revisor ortográfico focado em segurança. Ele barra falhas que poderiam permitir que golpistas injetassem códigos maliciosos ou roubassem dados do nosso banco.

5. Passo 5: SCA - Análise de Componentes (Grype)
O que faz: Analisa todas as bibliotecas e peças prontas da internet que foram importadas para dentro do projeto.

Importância: Funciona como a Vigilância Sanitária do código. Ele cruza as nossas dependências com um banco de dados mundial de vulnerabilidades conhecidas e impede o uso de ingredientes "vencidos" ou perigosos na aplicação.

6. Passo 6: Deploy Automático (GitHub Pages)
O que faz: Pega o conteúdo seguro da pasta src/ e faz a publicação oficial na internet.

Importância: Este passo só roda se todos os filtros anteriores derem sinal verde. Isso garante que o site que o cliente final acessa está 100% livre de vulnerabilidades mapeadas.
 Benefício de Negócio: O Conceito "Shift Left"
A grande vitória deste projeto foi trazer a segurança para o início do desenvolvimento (empurrar para a esquerda na linha do tempo, ou Shift Left).

Em vez de descobrirmos uma falha ou um vazamento quando o site já está no ar e recebendo clientes, nós descobrimos o erro enquanto o desenvolvedor ainda está escrevendo o código. Isso reduz custos de correção a quase zero e protege a reputação da empresa contra ataques digitais.
