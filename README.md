<h1>Gerenciador JDK</h1>

Gerenciador de ambiente JDK simples usando apenas script shell e dependências mínimas.

![Tela principal gerenciador-jdk](/imagens/tela-principal.png)  

<b>O que esse projeto faz?</b>

Ele padroniza a instalação e a alternância entre multiplas versões de OpenJDK num sistema Linux.

<b>O que esse projeto não faz?</b>
Ele não executa verificações de segurança no arquivo, portanto cabe ao usuário bom senso na obtenção de pacotes JDK.
Obtenha arquivos de fontes confiáveis, e verifique regularmente no site OpenJDK para a obtenção de atualizações de segurança.
Por exemplo obtenha pacotes seguros em: https://openjdk.org/install/

<b>Cenários de uso:</b>
Ambientes de desenvolvimento e uso pessoal. Não recomendo a atilização no estado atual em ambientes de produção. Para isso prefira uma
solução mais robusta como SDKMAN! https://sdkman.io/

<b> Vantagens de utilização:</b>
Simplicidade: A solução utiliza pouquíssimas dependências, muitas vezes já disponibilizadas numa instalação padrão Debian. O script pode
ser aprimorado por qualquer usuário comum pois é de fácil leitura e baixa complexidade. Ele concentra todas as funcionalidades em apenas 
um arquivo.
Controle total: O usuário pode obter a versão mais recente no próprio site e não fica dependente de disponibilização em repositório
centralizado. O gerenciador permite também a instalação de arquivos locais sem a utilização de conexões de internet o que facilita a criação
e reprodução de ambientes em multiplos equipamentos.
Aprendizado: Ao ler o script e tentar modificá-lo o usuário pode desenvolver novas habilidades no uso de shell script e perceber como ele pode automatizar
tarefas repetitivas.

<b> Como ele faz isso?</b>
Utilizando apenas 2 dependências (tar e wget) geralmente já pré instaladas em sistemas Debian e links simbólicos. O gerenciador
extrai o arquivo com o pacote jdk para pasta do usuário e organiza em pastas de acordo com o número da versão.  O script tenta 
extrair do nome do arquivo o número da versão. Caso ele não consiga solicita ao usuário o fornecimento manual da versão.
Ele pode promover a instalação de arquivos locais ou através de uma url. Utilizando apenas ferramentas nativas o script controla as 
variáveis de ambiente no basrc garantindo que elas apontem para a versão que o usuário deseja utilizar no momento.

<h2>Como instalar?</h2>

<b>No terminal com sua conta de usuário comum execute:</b>

```bash
wget -qO- https://raw.githubusercontent.com/souza-lb/gerenciador-jdk/refs/heads/main/instalar | bash
```
<b> Requisitos:</b>
* Sistema Debian 12 (ou demais sistemas baseados em Debian...)
* wget
* tar
* Conexão com internet disponível (apenas no momento da instalação)
* Espaço em disco (Pelo menos 300MB para instalação de um pacode JDK)

<b> Aviso importante!</b>
Não utilize a conta de superusuário para a instalação.

<h2>Como utilizar?</h2>

<b>No terminal com sua conta de usuário comum execute:</b>

```bash
gerenciador-jdk
```

Como não foi selecionada nenhuma opção será exibida a ajuda

![Tela ajuda](/imagens/tela-ajuda.png)  

Vamos prosseguir com a instalação de 2 versões do OpenJDK.

No terminal execute:

```bash
gerenciador-jdk instalar https://download.java.net/java/GA/jdk24.0.1/24a58e0e276943138bf3e963e6291ac2/9/GPL/openjdk-24.0.1_linux-x64_bin.tar.gz
```
Aguarde a finalização do processo de download

![Tela download](/imagens/tela-download.png)

