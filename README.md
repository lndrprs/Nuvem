
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
      - BlobStorage. 
    - Todas as storage accountes são criptografas usando Storage Service Encryption (SSE), para dados em descanso; 
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
    	 - Dados são copiados em 3 zonas na região primária, e assincronamente copiado para a região secundária;
    	 - Habilitar Read-Only Geo-Redundant Storage (RA-GRS), para acessar dados na região secundária. 
    	 
      - Geo-Zone-Redundant Storage (GZRS)
        - Redundância para alta disponibilidade e máxima durabilidade; 
    	 - Dados são copiados sincronizamente entre 3 zonas na região primária, e copiado assincronicamente para a região secundária; 
    	 - Permite habilitar Read-only Geo Zone Redundant Storage (RA-GZRS), para ler dados na região secundária. 
    	 
      - A mudança de redundância é um processo assincrono, sem SLA para término. Pode levar dias ou semanas, dependendo do tamanho da conta e região;
        - Durante a conversão, os dados permanecem acessíveis sem perda ou tempo de inatividade. 
    
  </div>
  </details>

</div> 
</details>

----


