
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
  <summary> 1.1 Designing Identity for Azure Solutions </summary>
  <div>

   - Microsoft Entra ID (Antigamente: Azure Active Directory)
   - Gerenciamento em Nuvem de Identidade e Acesso; 
   - Processo de Controle de Acesso:
     - Authentication: Verificar quem é o usuário / workload;
	   - Authorization: Determinar o que o usuário autenticado pode fazer.
	     - Quais recursos a identidade tem acesso? (Exemplo: Blob Storage);
	     - Quais ações a identidade pode performar no recurso? (Exemplo: Read, Write, Delete, etc.). 
	   

   - Opções de Controle de Acesso:
     - Credential-Based: Acesso é providenciado usando password, key ou token;
	     - Exemplos:
	       - Azure SQL User / Password;
		     - Storage Account Access Key;
		     - Storage Account SAS Token;
		     - Cosmos DB Access Key;
		     - Azure Event Hubs Access Key;
		     - Azure IoT Hub Shared Access Polity
		 
     - Identity-Based: Acesso é permitido para uma identidade do Entra ID.
	     - Exemplos:
	       - Entra ID App Registration & Enterprise Application;
	       - User-Assigned Managed Identity;
		     - System-Assigned Managed Identity;
		     - RBAC for Authorization. 
	   - Identity-Based é preferencial sob Credential-Based.
	   
	 - Tipos de Identidade no Entra ID:
	   - Humanos: Usuários, Grupos;
	   - Workloads: Service Principals (App REgistrations, Enterprise Apps, Managed Identities). 
	   
   - Azure Role-Based Access Control (Azure RBAC)
	   - Sistema de autorização que providencia acesso granular à recursos do Azure;
	   - Para atribuição de RBAC, precisa selecionar: 
	     - Assignee (Humano ou Workload);
	     - Role (Função);
	     - Scope (Recurso).  
	   
	 - Funções Embutidas no RBAC (Roles):
	   - General:
	     - Owner;
		   - Contributor;
		   - Reader;
		   - User Access Administrator;
		   - etc.
		 
	   - Resource-Specific:
	     - Storage Blob Data Owner;
		   - IoT Hub Data Reader; 
		   - etc. 
		 
	 - Escopos do RBAC: 
	   - Management Groups;
	   - Subscription;
	   - Resource Group;
	   - Individual Resource. 
	   
	 - Permite customizar funções / roles via JSON, se as embutidas não servirem. 
	 
   - Melhores Práticas para Autenticação 
     - Não user contas de usuários para Workloads. Criar um Service Principal;
     - Usar grupos ao invés de atribuir permissões a usuários individualmente; 
	   - Aplicar sign-in passwordless para usuários (Se aplicável / suportado);
	   - Proteja recursos usando Conditional Access Policies, e Privileged Identity Management (PIM). 
	   - Proteja senhas de usuários usando MFA e Identity Protection. 
	 
   - Conditional Access Policies 
     - Políticas de Acesso aplicadas após a autenticação de primeiro-fator é completada com sucesso; 
	   - As políticas de acesso condicional permitem ou bloqueiam o acesso baseado nas condições definidas. 
	   - Exemplos:
	     - Exigir MFA para Dispositivos iOS;
	     - Bloquear acesso fora de determinado país;
	     - Exigir Dispositivo em conformidade para Admins. 
	 
   - Privileged Identity Management (PIM)
     - Providencia acesso just-in-time para funções RBAC;
	   - O acesso é removido após a data de expiração;
	   - Capacidades: 
	     - Atribução com prazo definido para funções; 
	     - Pode exigir aprovação de um Admin para ativar uma função;
	     - Pode obrigador MFA para ativar uma função;
	     - Requisita Justificativa para Auditorias Futuras;
	     - Envia notificações quando uma função é ativada;
	     - Histórico de Ativação disponível para download, para Auditorias.   


  </div>
  </details>

  <details>
  <summary> 1.2 Designing Governance For Azure Solutions </summary>
  <div>

   - Azure Governance
     - Controla como os recursos são criados e gerenciados, para entrar em conformidade com o governo indústria e padrões de segurança;
     - Quanto maior a necessidade de conformidade, menor a agilidade de equipes. 

   - Microsoft Azure Well-Achitected Framework:
     - Reliability;
     - Security;
     - Cost Optimization;
     - Operational Excellence; 
     - Performance Efficiency.  

   - Azure Policy 
     - É ferramenta que compele / força a governança, em escala;
     - Exemplos de Policy Definitions:
       - Todas as Storage Accounts devem bloquear acesso público;
       - Azure Key Vaults devem ter o serviço de Firewall ativo;
       - Todos os recursos em uma assinatura devem ser provisionados em determinado país;
       - Usuários não são permitidos para criar VMs de GPU. 

     - Usando Políticas:
       - Primeiro, encontre a Policy Definition que combine com o requisito;
       - Depois, decida o escopo onde a Policy precisa controlar; 
       - Atribua / Assign a Policy Definition ao Escopo. 

     - Policy Definition
       - Tipos de Policy Definition:
         - É possível escolher entre várias que a própria Microsoft gera;
         - Usar Policy Initiatives se precisa de conformidade de alguma indústria específica, como Saúde, Cartões, etc. (Não é dimensionável);
         - Criar sua própria política. 
         
    - Policy Scope
      - Podem ser atribuídas em:
        - Management Group;
        - Subscription;
        - Resource Group;
        - Alguns recursos individuais.  

    - Policy Assignment 
      - Atribuição da Policy ao Escopo.     

    - Azure Policy Effect 
      - Ação quando a política é violada, por algum recurso não conforme:
        - Audit: Cria um alarme, e não bloqueia o provisionamento;
        - Deny: Bloqueia o provisionamento;
        - Modify: Adiciona, atualiza, ou remove propriedades de provisionamento de recursos. 

      - Nem todos os efeitos são suportados por todas as policies. 

  </div>
  </details>  

  <details>
  <summary> 1.3 Designing Incident Response and Monitoring For Azure Solutions </summary>
  <div>

   - 

  </div>
  </details>    

</div> 
</details>

----


