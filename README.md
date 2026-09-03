
----

<div align="center">
<h4>

███╗░░██╗██╗░░░██╗██╗░░░██╗███████╗███╗░░██╗░██████╗
████╗░██║██║░░░██║██║░░░██║██╔════╝████╗░██║██╔════╝
██╔██╗██║██║░░░██║╚██╗░██╔╝█████╗░░██╔██╗██║╚█████╗░
██║╚████║██║░░░██║░╚████╔╝░██╔══╝░░██║╚████║░╚═══██╗
██║░╚███║╚██████╔╝░░╚██╔╝░░███████╗██║░╚███║██████╔╝
╚═╝░░╚══╝░╚═════╝░░░░╚═╝░░░╚══════╝╚═╝░░╚══╝╚═════╝░
</div>
</h5>

----

<details>
  <summary><b> 1. Azure </b></summary>
<div align="Left"> 

<br>

  <details>
  <summary> 1.1 Core Architectural Components of Azure </summary>
  <div>

   - Categorias de Serviços do Azure:
     - Compute:
       - Virtual Machines;
       - App Service;
       - Azure Functions;
       - Container Apps;
       - Azure Kubernetes Service. 

     - Networking: 
       - Virtual Network;
       - Load Balancer;
       - VPN Gateway;
       - ExpressRoute;
       - Azure DNS.

     - Storage:
       - Blob Storage;
       - Azure Files;
       - Queue Storage;
       - Table Storage;
       - Managed Disks. 

     - Databases:
       - Azure SQL;
       - Azure Cosmos DB;
       - PostgreSQL Flex;
       - MySQL Flex;
       - Redis Cache. 

     - AI + ML:
       - Azure OpenAI;
       - AI Services;
       - Machine Learning; 
       - Bot Service;
       - AI Search. 

     - Identity + Security:
       - Microsoft Entra ID;
       - Key Vault;
       - Defender for Cloud;
       - DDoS Protection;
       - Firewall. 

     - DevOps + Management:
       - Azure DevOps;
       - Azure Monitor;
       - ARM Template;
       - Azure Policy;
       - Cost Management. 

     - IoT:
       - IoT Hub; 
       - IoT Central;
       - Digital Twins;
       - Stream Analytics;
       - Event Hubs. 

     - Analytics:
       - Synapse Analytics;
       - Data Factory;
       - Databricks;
       - HDInsight;
       - Azure Data Explorer. 

     - Integration:
       - Logic Apps; 
       - API Management;
       - Service Bus;
       - Event Grid;
       - Notification Hubs. 

   - Azure Accounts
     - O primeiro passo para utilizar recursos na Azure, é possuir uma conta; 
     - Dentro da conta, você terá as assinaturas / subscrições;
     - Dentro das assinaturas, você tem os Resource Groups / Grupos de Recursos;
     - Dentro dos Resources Groups, você tem os Recursos.

     - Azure Account -> Subscription -> Resource Groups -> Resources. 

   - Azure Physical Infrastructure
     - A infraestrutura do Azure começa com os Datacenters; 
     - Os datacenters são servidores organizados em racks, com energia dedicada, resfriamento e infraestrutura de rede; 
     - Existem datacenter ao redor do mundo, e são agrupador em Azure Regions e Azure Availability Zones, que providenciam resiliência e confiabilidade. 

     - Geografia -> Region -> Availability Zone -> Datacenter.       

     - Region: Área no planeta que possui pelo menos 1, mas múltiplos datacenters que estão próximos e interligados com baixa latência;
     - Availability Zone: Datacenters separados fisicamente dentro do Azure Region. Cada região possui 1 ou mais datacenters.

   - Observações:
     - Recursos só podem pertencer a um Resource Group ao mesmo tempo;
     - Quando uma ação ou configuração é feita em um Resource Group, os recursos atuais e futuros herdam essa configuração.


  </div>
  </details>

  <details>
  <summary> 1.2 Azure Virtual Machines </summary>
  <div>

   - Azure Virtual Machines
     - Servidores Virtualizados no Azure, como IaaS; 
     - Assim como um servidor físico, o cliente controla o sistema operacional e o software instalado;
     - Fácil provisionamento através de imagens já predefinidas;
     - Boas opções, quando:
       - Precisa de controle total sob Sistema Operacional;
       - Executar softwares Customizados;
       - Configurações Customizadas. 

     - Casos de Uso para VMs:
       - Teste e Desenvolvimento: Diferentes Sistemas Operacionais e Configurações de Aplicações;
       - Hospedagem em Nuvem: Dimensionamento conforme demanda;
       - Extensão de Datacenter: Estende a rede on-premises no Azure, e hospeda as cargas de trabalho em uma VNet;
       - Disaster Recovery: Mantém capacidade failover no Azure e executa workloads críticos se o site primário estiver indisponível;
       - Lift and Shift Migration: Move Workloads existentes com reformulação mínima de aplicação. 

     - Recursos e Tamanhos
       - Size: Propósito, número de núcleos de processamento, quantidade de RAM;
       - Storage Disks: HDD, SSD, etc.;
       - Networking: VNet, Public IP, Configuração de Porta. 
       - Cada VM permite customizar as opções:
         - vCPU: Afeta a capacidade de processamento;
         - RAM: Afeta quantos dados ficam na memória da VM;
         - Disk: Afeta capacidade de Armazenamento, IOPS e Vazão; 
         - Network: Performance da transferência para a VM e Fora dela; 
         - Premium SSD: Indica se suporta discos premiums gerenciáveis;
         - Generation: Indica a geração da plataforma e pode afetar performance base. 

       - Leitura de Nomes:
         - Standard_D2s_v5 
           - D = Família;
           - 2 = vCPUs;
           - s = Disco Premium.
           - v5 = Geração do Hardware. 

     - Famílias de VMs  
  
     | Letra |  Foco | Exemplos |
     |-------|-------|----------|
     | B - Bustable | Expansível e Econômico | Workloads de Dev. / Test com Picos de CPU ocasionais |
     | D - General  | Propósitos Gerais | Servidores Web, Servidores de Aplicações Pequenas - Medianas | 
     | E - Memory   | Otimizado para Memória | Bancos de Dados em Memória, Workloads de Analytics | 
     | F - Compute  | Otimizado para Computação | Aplicações de uso intensivo de CPU |
     | M - Large Memory | Alto Consumo de Memória | Bancos de Dados Empresariais | 
     | L - Storage  | Otimizado para Armazenamento | Alto desempenho para processamento de Dados e Armazenamento |
     | N - GPU      | GPU Ativada | Treinamento de IA e Workloads de Gráficos |  
  
     - Virtual Machine Scale Sets 
       - Permite Criar e Gerenciar grupos de VMs idênticas, e com balanceamento de carga; 
       - Centraliza a configuração e pode automaticamente dimensionar horizontalmente sob demanda ou agendamento; 
       - Também é integrado com balanceamento de carga, então o tráfego é distribuído eficientemente. 

     - Virtual Machine Availability Sets 
       - Melhora a resiliência da VM dentro de uma região; 
       - Reduz a chance de todas as VMs serem afetadas por uma manutenção ou falha de hardware; 
       - Availability Sets são divididos em dois grupos:
         - Update Domain: VMs que podem ser reiniciadas juntas durante a manutenção planejada;
         - Fault Domain: VMs que um ponto de falha em energia ou rede; 
       - É uma redundância em nível de VM. 

  </div>
  </details>   

  <details>
  <summary> 1.3 Azure Virtual Desktop </summary>
  <div>

   - Serviço de Aplicação e Virtualização no Azure; 
     - Permite os usuários acessarem, com segurança, Windows Desktops e aplicações atarvés de dispositivos e locais;
     - Ao invés das informações ficarem no dispositivo físico, ficam na nuvem. 
     - É integrado com o Microsoft Entra ID para controle de acesso e identidade; 
     - Ajuda a reduzir exposição de dados em dispositivos locais.

  </div>
  </details>        

  <details>
  <summary> 1.4 Azure Containers </summary>
  <div>

   - Contêineres 
     - São usados para arquiteturas de microsserviços; 
     - Nessa arquitetura, as soluções são separadas em partes independentes:
       - Um contêiner hospeda o front end, outro o back end e outro o armazzenamento; 
       - Separando dessa forma, permite manter, dimensionar, ou atualizar cada parte da aplicação, independentemente. 

   - Azure Container Instances 
     - A forma mais rápida e simples de executar contêineres na nuvem, sendo PaaS.
     
   - Azure Container Apps
     - Também é um serviço PaaS, mas possui Balanceador de Carga e Dimensionamento;
     - O projeto pode se adaptar a mudança de demanda. 

   - Azure Kubernetes Service 
     - Orquestração de Contêineres, que gerencia o ciclo de vida de contêineres. 

  </div>
  </details>     

  <details>
  <summary> 1.5 Azure Functions </summary>
  <div>

   - Functions 
     - Processamento baseado em evento, serverless, que não requer VMs ou Contêineres; 
     - Um evento "ativa" as Functions, como uma requisição REST, um Timer ou Mensagem de outro serviço Azure; 
     - Podem ser dimensionadas automaticamente, baseadas em demanda;
     - Azure cobra apenas pelo tempo de CPU usado enquanto a Function roda;
     - Existem dois tipos de Functions:
       - Stateless: Reinicia sempre que responde a um evento;
       - Stateful: Tem um contexto da atividade anterior. 

  </div>
  </details> 

  <details>
  <summary> 1.6 IoT and Edge Services </summary>
  <div>

   - IoT Services 
     - IoT Hub: Permite comunicação segura e bi-direcional entre serviços da nuvem e dispositivos IoT;
     - IoT Central: Plataforma SaaS para construção de Soluções; 
     - IoT Edge: Estende as capacidades da nuvem para dispositivos edge, executando alguns workloads mais próximos de onde os dados são gerados. 

  </div>
  </details>       

  <details>
  <summary> 1.7 Azure App Service </summary>
  <div>

   - App Service 
     - É um serviço baseado em HTTP;
     - Permite criar e hospedar na linguagem que deseja, sem infraestrutura:
       - Web Apps; 
       - API apps;
       - WebJobs;
       - Background Jobs; 
       - Mobile Back-Ends; 
     - Oferece alta disponibilidade e dimensionamento automático; 
     - Suporta Windows e Linux, e também provisionamentos automáticos do GitHub, Azure DevOps ou qualquer repositório Git; 
     

  </div>
  </details>  

  <details>
  <summary> 2.1 Storage Accounts </summary>
  <div>

   - Storage Account 
     - Único namespace para seus dados no Azure, acessível de qualquer lugar no mundo através de HTTP / HTTPS; 
     - Os dados nessa conta são protegidos, altamente disponíveis, duráveis e massivamente dimensionáveis; 
     - Ao criar a conta, precisa escolher qual tipo de conta deseja;
     - O tipo de conta define os serviços de armazenamento e as opções de redundância, tendo impacto em casos de uso. 

     - Tipos:
       - Standard General-Purpose v2 
         - Serviços Suportados:
           - Blob Storage (Incluindo Data Lake Storage);
           - Queue Storage;
           - Table Storage; 
           - Azure Files.
         - Redundâncias Suportadas:
           - LRS; 
           - GRS; 
           - RA-GRS;
           - ZRS;
           - GZRS;
           - RA-GZRS. 
         - Padrão de armazenamento para blobs, file shares, queues e tables; 
         - Recomendado para a maioria dos cenários usando Azure Storage;
         - Caso seja necessário utilizar NFS (Network File System) em Azure Files, usar o Premium File Shares. 

      - Premium Block Blobs
        - Serviço Suportado:
          Blob Storage (Incluindo Data Lake Storage).
        - Redundância Suportadas:
          - LRS;
          - ZRS.
        - Para Block Blobs e Append Blobs; 
        - Recomendado para cenários com alta frequência de transações / baixa latência ou que usam objetos pequenos.

      - Premium File Shares 
        - Serviço Suportado:
          - Azure Files 
        - Redundâncias Suportadas:
          - LRS;
          - ZRS. 
        - Recomendado para alto dimensionamento de aplicações ou alta performance; 
        - Storage account que permite SMB e NFS como compartilhamento de arquivos. 

      - Premium Page Blobs 
        - Serviços Suportados:
          - Page Blobs; 
        - Redundância Suportada:
          - LRS.
        - Storage Account para Page Blobs apenas (Como VM Disks).

   - Endpoints 
     - Blob Storage: https://(nome).blob.core.windows.net
     - Data Lake Storage Gen2: https://(nome).dfs.core.windows.net
     - Azure Files: https://(nome).file.core.windows.net
     - Queue Storage: https://(nome).queue.core.windows.net
     - Table Storage: https://(nome).table.core.windows.net

  </div>
  </details>               

  <details>
  <summary> 2.2 Azure Storage Redundancy </summary>
  <div>

   - Redundancy 
     - Azure Storage mantém múltiplas cópias dos dados para proteger contra falhas de hardware, energia e desastres regionais;
     - As opções de redundância determinam disponibilidade, durabilidade e custos;
     - Ao escolher a redundância, balancear o menor custo com a maior disponibilidade;
     - Fatores para consideração:
       - Como os dados são replicados na região primária;
       - Se os dados são replicados para uma segunda região, geograficamente distante da primeira, para proteção contra desastres;
       - Se a aplicação querer leitura de dados replicados na segunda região, se a primeira estiver indisponível. 

     - Redundância na Região Primária 
       - Os dados são sempre replicados 3x na região primária; 
       - Opções:
         - Locally Redundant Storage (LRS):
           - Replica os dados 3x dentro de um data center na região primária; 
           - Possui 11 9's (99.999999999%) 
           - É a opção mais barata, e prote contra falhas de rack de servidores e drives;

         - Zone-Redundant Storage (ZRS):
           - Replica os dados sincronizadamente através de 3 zonas de disponibilidade na região primária;
           - Possui durabilidade de 12 9's (99.9999999999%)
           - Os dados ficam disponíveis para leitura e escrita mesmo que uma zona esteja indisponível;
           - Azure performa atualizações de redes, como reapontamento de DNS. 

     - Redundância na Região Secundária 
       - Quando você cria uma Storage Account, você escolhe a região primária. Azure atribui a região secundária emparelhada em pares de regiões;
       - Por padrão, dados de região secundária não são legíveis até que ocorra o failover. Se a região primária está indisponível, você pode fazer o fail, assim a região secundária vira a primária.
       - O intervalo entre a escrita mais recente na região primária e a última escrita na secundária é RPO - Recovery Point Objective;
         - O RPO indica o ponto no tempo onde os dados podem ser recuperados; 
         - Normalmente Azure Storage possui um RPO de menos de 15 minutos, mas não há um SLA de quanto tempo leva para replicar os dados à região secundária. 
       - Opções:
         - Geo-Redundant Storage (GRS)
           - Copia os dados 3x na região primária (LRS) e assincronicamente para a região secundária (LRS)      
           - Provê 16 9's no Ano. 

         - Geo-Zone-Redundant Storage (GZRS)
           - Os dados são copias em 3 zonas na região primária, e replicados para a secundária usando LRS (3x no Datacenter distante - LRS)

       - Para ler os dados na região secundária antes do failover, precisa ativar o RA-GRS: Read Access Geo-Redundant Storage, ou RA-GZRS.  
     

  </div>
  </details>       

  <details>
  <summary> 2.3 Storage Services </summary>
  <div>

   - Azure Storage inclui esses serviços de dados:

     - Azure Blobs: Armazenamento de objetos massivamente escalável, para texto, dados binários e big data analytics (Data Lake Storage Gen2);
       - Níveis de Armazenamento:
         - Hot Access Tier: Dados acessados frequentemente;
         - Cool Access Tier: Dados acessados infrequentemente, no mínimo 30 dias;
         - Cold Access Tier: Dados acessados infrequentemente, no mínimo 90 dias;
         - Archive Access Tier: Dados raramente acessados, no mínimo 180 dias. 

     - Azure Files: File Shares gerenciáveis para Cloud ou On-Premises;
       - Oferece file shares na nuvem que são acessíveis via SMB ou NFS;
       - Podem ser montados simultaneamente por provisionamentos em nuvem ou on-premises.

     - Azure Queues: Armazenamento de mensagens entre componentes de aplicação;
       - Queues são acessados por chamadas HTTP/HTTPS;
       - Armazena mensagens até 64 KB;
       - Comumente emparelhado com Azure Functions, para mensagens ativarem ações em background. 

     - Azure Disks: Volumes de Armazenamento em nível de Block, para VMs do Azure;
     - Azure Tables: tabela NoSQL para dados não relacionais.

  </div>
  </details>       

  <details>
  <summary> 2.4 Data Migration Options </summary>
  <div>

   - Azure Migrate 
     - Migra de ambientes On-Premises para a Nuvem; 
     - Funciona como um Hub, ajudando a gerenciar e avaliar a migração ao Azure:
     - Funcionalidades:
       - Um portal para começar, executar e rastrear a migração ao Azure;
       - Possui o Azure Migrate: Discovery e o Azure Migrate: Server Migration;

   - Azure Data Box 
     - Serviço físico de migração, que transfere grandes quantidades de dados ao dispositivo de storage Data Box; 
     - Esse dispositivo tem a capacidade de 80 TBs; 
     - Pode ser usado para importar ou exportar dados do Azure; 
     - Normalmente usado quando a banda de rede é limitada.
       - Cenários:
         - Migração em massa, de uma vez, dos dados locais ao Azure;
         - Quando a transferência Online é muito demorada.

  </div>
  </details>       

  <details>
  <summary> 2.5 Azure File Movement Options </summary>
  <div>

   - AzCopy 
     - Utilidade CLI que copia Blobs ou Arquivo de / para sua Storage Account;
     - Permite fazer upload de arquivos, download, copiar entre storage accounts, e até sincronizar arquivos;
     - Blobs ou Files possui sincronização unilateral, definindo a origem e destino, e o AzCopy é executado nessa direção. 

   - Storage Explorer
     - Aplicação que providencia uma GUI para gerenciamento de arquivos e blobs na Azure Storage Account; 
     - Funciona no Windows, macOS e Linux, e usa o AzCopy como backend para performar as tarefas. 

   - Azure File Sync 
     - Ferramenta que permite centralizar File Shares no Azure Files, mantendo a flexibilidade, performance e compatibilidade do Windows File Server; 
     - Como se fosse transformar o File Server em uma CDN - Content Delivery Network; 
     - Assim que instalar o File Sync no Windows Server, automaticamente fica sincronizado bidirecionalmente com os arquivos no Azure; 
     - Características:
       - Usar qualquer protocolo disponível no Windows Server para acessar seus dados localmente, incluindo SMB, NFS e FTPS;
       - Ter quantos caches precisar, no mundo todo;
       - Substituir um servidor que falhou, instalando o Azure File Sync em um novo servidor no mesmo datacenter.

  </div>
  </details>       

  <details>
  <summary> 3.1 Azure Identity, Access and Security </summary>
  <div>

   - Azure Authentication Methods 
     
     - Single Sign-On
       - Permite o usuário entrar uma vez, e acessar múltiplas aplicações confiáveis.

     - Multifactor Authentication
       - Incita o usuário por um fator extra durante o processo de entrada. Uma senha não é o suficiente para acesso.

     - Passwordless Authentication
       - Elimina a senha completamente, substituindo com um dispositivo confiável e uma biometria ou PIN; 
       - Microsoft Entra ID suporta 3 opções passwordless:
         - Windows Hello for Business: Credenciais usadas no próprio Windows, sendo biometria ou PIN;
         - Microsoft Authenticator App: Usado para confirmar a entrada;
         - FIDO2 Security Keys: Dispositivos que possuem USB, Bluetooth ou NFC. 

  </div>
  </details>    

  <details>
  <summary> 3.2 Azure External Identities </summary>
  <div>

   - External Identity
     - Pessoa, Dispositivo ou Serviço que existe fora do seu Tenant;
     - Organizações precisam colaborar com parceiros, fornecedores, vendedores e contratados; 
     - Essas identidades externas podem usar seus recursos com as credenciais existentes deles. 

   - External ID Capabilities 
     - B2B Collaboration: Usuários externos se conectam nas suas aplicações como Guest Users;
     - B2B Direct Connect: Conectividade entre o seu tenant, e o do parceiro; 
     - External ID For Customers (B2C): Publicação de aplicações SaaS ou customizadas para clientes / consumidores. 

  </div>
  </details>      

  <details>
  <summary> 3.3 Azure Conditional Access </summary>
  <div>

   - Ferramenta do Entra ID que permite / nega acessos a recursos se baseando em sinais de identidade; 
   - Esses sinais incluem: 
     - Usuário ou Grupo a que pertence;
     - Local do IP;
     - Dispositivo;
     - Aplicação alvo;
     - Risco em tempo real de Entrada. 

  </div>
  </details>        

  <details>
  <summary> 3.4 Azure Role-Based Access Control </summary>
  <div>

   - Azure RBAC 
     - Controle de acesso através de escopos, com funções embutidas (Owner, Reader, Contributor, Custom);
     - Os escopos podem ser: Management Group, Subscription, Resource Group, Resource;
     - As permissões de níveis inferiores são herdadas dos níveis superiores;
       - Sendo Management Group o nível maior, e o Resource individual o nível menor. 

   - Zero Trust Model 
     - Modelo que assume que acontecerá o pior cenário, e protege os recursos com essa expectativa; 
     - Os 3 princípios: 
       - Verificar Explicitamente a autenticação e autorização;
       - Acesso de Menor Privilégio: Limitar os acessos com JIT e JEA, políticas e proteção de dados;
       - Assuma Invasão: Para limitar o potencial impacto e acesso segmentado. 

  </div>
  </details>       

  <details>
  <summary> 3.5 Encryption and Key Management in Azure </summary>
  <div>

   - Encryption
     - Encryption at Rest: Protege os dados quando armazenados, como em bancos de dados, discos e storage accounts;
       - Exemplos: AES-256 / Service Managed Keys;
     - Encryption in Transit: Protege os dados enquanto eles se movem entre serviços, aplicações e usuários. 
       - Exemplos: TLS / HTTPS/ VPN Tunnels. 

   - Azure Key Vault
     - Serviço para armazenar de forma segura, e controlar os acessos, à:
       - Secrets (Connection Strings e Passwords);
       - Encryption Keys;
       - Certificates.   
     - Centraliza o gerenciamento de segredos e chaves ao invés de inserir no código diretamente ou nas configurações. 
       - Usando o Vault, ajuda a:
         - Controlar quem acessa as chaves e segredos; 
         - Rotacionar e atualizar chaves ao longo do tempo;
         - Auditar uso de chave e segredos. 

  </div>
  </details>      

  <details>
  <summary> 3.6. Microsoft Defender for Cloud </summary>
  <div>

   - Defender for Cloud 
     - Serviço de proteção contra ameaças e gerenciamento de segurança; 
     - Monitora a Cloud, On-Premises, Hybrid, e Multicloud, providenciando recomendações e alertas; 
     - Ajuda a fortalecer recursos, rastrear riscos, e responder a ameaças. No Azure, é nativamente integrado. 
     - Proteções Azure-Native:
       - Azure PaaS Services;
       - Azure Data Services; 
       - Networks. 
       
     - Para Proteções On-Premises, precisaria provisionar o Azure Arc e ativar o Defender for Cloud. 

  </div>
  </details>        


</div> 
</details>

----


