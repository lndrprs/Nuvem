
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
  <summary> 2.1 Azure App Service </summary>
  <div>

   - 
     

  </div>
  </details>                  


</div> 
</details>

----


