
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
  <summary> 1.2 Azure Compute Services </summary>
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
       - Size: Propósito, número de números de processamento, quantidade de RAM;
       - Storage Disks: HDD, SSD, etc.;
       - Networking: VNet, Public IP, Configuração de Porta. 

     - Famílias de VMs 
     
     | Letra | Descrição | Foco | Exemplos |
     |-------|-----------|------|----------|
     | B | Bustable | Expansível e Econômico | Workloads de Dev. / Test com Picos de CPU ocasionais |

  </div>
  </details>   

</div> 
</details>

----


