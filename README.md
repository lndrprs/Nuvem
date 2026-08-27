
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
  <summary> 1.1 Storage Accounts </summary>
  <div>

    - Uma conta de Azure Storage contém: Blobs, Files, Queues, Tables e Discos; 
    - Tipos de Contas de Storage: 
      - General-Purpose (v2 e v1); 
      - BlockBlobStorage; 
      - FileStorage;
      - Page Blobs
      - BlobStorage (Legado). 
    - Todas as storage accounts são criptografas usando Storage Service Encryption (SSE), para dados em descanso; 
    - A movimentação de dados entre diferentes storage accounts pode ser  feita automaticamente ou manualmente;
      - Manualmente, pode usar:
       - AzCopy (CLI utility);
    	 - Data Movement Library (Projeto para alta performance, confiável, e oprações de transferências fáceis similares ao AzCopy);
    	 - REST API ou Client Library permite criar uma aplicação customizada para migrar dados. 
    
    
    - Endpoints das Storage Accounts:
      - Blob Storage:                 https://domínio.BLOB.core.windows.net
      - Table Storage:                https://domínio.TABLE.core.windows.net
      - Queue Storage:                https://domínio.QUEUE.core.windows.net
      - Azure Files:                  https://domínio.FILE.core.windows.net
      - Azure Data Lake Storage Gen2: https://domínio.DFS.core.windows.net
    
      
    - Níveis de Acesso:
      - Hot 
        - Custo de armazenamento mais alto / Menor custo de acesso entre todos os 4;
    	 - Dados acessados frequentemente;
    	 - Por padrão, novas Storage Accounts são criadas com Hot Tier. 
    	 
      - Cool 
        - Menor custo de armazenamento, mas maior custo de acesso; 
    	 - Dados que são acessados infrequentemente (Pelo menos 30 dias);
    	 - Pode ser usado para backup de curto prazo.
    	 
      - Cold 
        - Menor custo de armazenamento, e mais custo de acesso em comparação ao Cool 
    	 - Dados que são raramente acessados (Pelo menos 90 dias);
    	 - Ideal para economia de conjuntos grandes de dados.
      
      - Archive
        - O menor custo de armazenamento, mas o maior custo de recuperação;
    	 - Dados que são raramente acessos (Pelo menos 180 dias);
    	 - Dados que precisam ser armazenados por muito tempo. 
    	 
      • Políticas de Blob Lifecycle Management podem automatizar as transições entre níveis e expiração baseado em regras; 
        - Mudanças de políticas podem levar 24 horas para ter efeito;
        - Custos operacionais padrões são aplicados para chamadas ao Set Blob Tier API. 
    
    
    - Storage Redundancy  	 
      - Locally Redudant Storage (LRS) 
        - Baixo Custo;
    	 - Dados são copiados sincronicamente 3x dentro da região primária.
    	 
      - Zone Redudant Storage (ZRS)  
        - Alta disponibilidade; 
    	 - Dados são copiados sincronicamente para 3 zonas na região primária.
    	 
      - Geo Redundant Storage (GRS)
        - Redundância Inter-Regional;
    	 - Dados são copiados em 1 local físico na região primária (LRS), e assincronamente copiado para a região secundária;
    	 - Habilitar Read-Only Geo-Redundant Storage (RA-GRS), para acessar dados na região secundária. 
    	 
      - Geo-Zone-Redundant Storage (GZRS)
        - Redundância para alta disponibilidade e máxima durabilidade; 
    	 - Dados são copiados sincronizamente entre 3 zonas na região primária (ZRS), e copiado assincronicamente para a região secundária; 
    	 - Permite habilitar Read-only Geo Zone Redundant Storage (RA-GZRS), para ler dados na região secundária. 
    	 
      - A mudança de redundância é um processo assíncrono, sem SLA para término. 
        - Pode levar dias ou semanas, dependendo do tamanho da conta e região;
        - Durante a conversão, os dados permanecem acessíveis sem perda ou tempo de inatividade.  

    - Tipos de Storage Accounts 
      - General-Purpose v2 Accounts
        - Suporta:
          - Data Lake Gen2 
          - Blobs 
          - Files 
          - Disks
          - Queues 
          - Tables 
        - Entrega o menor preço por gigabyte para Azure Storage.

      - BlobStorage Accounts 
        - Binary Large Object (BLOb)
        - Armazena Imagem, Vídeo, Áudio, Logs, Backups, etc; 
        - Acessível através de REST API, Powershell e Azure CLI; 
        - Organização via Contêiner, junta blobs similares num diretório. 
        - Apenas suporta Blobs Block e Append;
        - BlobStorage apenas oferta performance padrão. BlockBlobStorage suporta performance premium; 
        - Legacy BlobStorage está sendo retirado.

        - Tipos de Blob:
          - Block: Binários e Textos até 4.8 TB, blobs maiores até 190.7 TiB 
          - Append: Ideal para dados de logs de VM's; 
          - Page: armazena arquivos de acesso aleatório em até 8 TB e arquivos VHD. 

        - Níveis de Acesso:
          - Hot; 
          - Cool;
          - Archive.  

          - Obs.: Permite gerenciamento de ciclo de vida. 

        - Características do Blob 
          - Permite Versionamento;
          - Snapshots; 
          - Replicamento entre Contas; 
          - Permite Website Estático.
 

      - FileStorage Accounts 
        - Apenas suporta compartilhamentos de arquivo; 
        - Oferece bursting de IOPS 


  </div>
  </details>

  <details>
  <summary> 1.2 Compute Services </summary>
  <div>

    - Azure App Service 
      - PaaS para desenvolvimento, provisionamento e escalonamento de aplicações Web;
      - Possui diferentes tipos de Serviços App: 
        - Web Apps: Aplicações e Websites;
        - Web Apps for Containers: Aplicações Conteinerizadas;
        - API Apps: Exposição e Conexão para dados em Backend;
        - Sidecar Extensions: Contêineres adicionais para aplicação principaç; 
        - Webjobs on Linux: Tarefas em backgroind junto com aplicações web;
        - AI/ML Features: Execução de SLMs como sidecars. 
      - Automaticamente atualiza e mantém o Sistema Operacional e Frameworks de Linguagem;
      - Pode escalar para cima ou aos lados, manualmente ou automaticamente; 
      - Suporta as linguagens:
        - .NET
        - .NET Core
        - Java
        - Ruby
        - Node.js
        - PHP
        - Python
        - Runtimes Ubuntu 

      - App Service Plan: Conjunto de recursos computacionais necessários para um Web App rodar; 
      - Cada App Service Plan consiste de uma região, número e tamanho das VMs e Nível de Preço;
      - Níveis de Preços:
        - Shared Compute (Free e Shared): Não permite escalar horizontalmente. Possui cotas de CPU;
        - Dedicated (Basic, Standard, Premium e PremiumV2): Quanto maior o nível, mais VMs para dimensionar horizontalmente;
        - Isolated: Uma VM dedicada que providencia dimensionamento horizontal máximo. 

  </div>
  </details>  

</div> 
</details>

----


