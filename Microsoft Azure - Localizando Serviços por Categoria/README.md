# Microsoft-Azure-Service

Microsoft Azure oferece uma ampla variedade de serviços agrupados em categorias para atender às necessidades de diferentes tipos de soluções. Como **computação em nuvem (SaaS, PaaS)**, entre outros.

---------------------------------------------------------------------------------------------------------------------------------

### **Localizando Serviços por Categoria**
Você pode navegar pelas categorias no portal do Azure ou usar a [Documentação do Azure](https://azure.microsoft.com/pt-br/documentation/).

#### **Serviços Principais em Computação na Nuvem**
- **SaaS (Software as a Service):**
  - Exemplo: **Microsoft 365**, **Dynamics 365** e **Power BI**.
  - Esses serviços são gerenciados inteiramente pela Microsoft e podem ser acessados diretamente pelos usuários.

- **PaaS (Platform as a Service):**
  - Oferece infraestrutura e ferramentas para desenvolver, testar e gerenciar aplicativos sem gerenciar servidores ou hardware.
  - **Principais Serviços:**
    - **Azure App Services**: Hospedagem de aplicativos Web e APIs.
    - **Azure Functions**: Execução de código sem gerenciar servidores.
    - **Azure Kubernetes Service (AKS)**: Gerenciamento de contêineres.

#### **Como Acessar Categorias no Portal do Azure**
1. Acesse o portal do Azure: [https://portal.azure.com](https://portal.azure.com).
2. No menu lateral, clique em **"Todos os Serviços"**.
3. Utilize o filtro para encontrar categorias como:
   - **Compute** (Computação)
   - **Databases** (Bancos de Dados)
   - **Storage** (Armazenamento)
   - **AI + Machine Learning**

-----------------------------------------------------------------------------------------------------------------------------------

### **Criando um Banco de Dados no Azure**
Você pode criar diferentes tipos de banco de dados no Azure, como SQL, NoSQL e armazenamento de dados em tempo real.

#### **Exemplo: Criando um Banco de Dados SQL**
1. **No portal do Azure:**
   - Vá para **Todos os Serviços > Bancos de Dados > Azure SQL**.
2. Clique em **+ Criar** e escolha entre:
   - **Banco de Dados Único**: Uma instância independente do SQL.
   - **Pool Elástico**: Para compartilhar recursos entre várias instâncias.
   - **Gerenciado (Managed Instance)**: Para migração de bancos locais para a nuvem.
3. Preencha os detalhes como:
   - **Nome do Servidor**
   - **Região**
   - **Camada de Preço** (Escolha baseada no desempenho desejado).
4. Configure as regras de firewall para permitir o acesso ao banco.
5. Clique em **Revisar + Criar** para provisionar.

#### **Exemplo: Criando um Banco NoSQL com Cosmos DB**
1. No portal, acesse **Azure Cosmos DB**.
2. Escolha o tipo de banco: MongoDB, Cassandra, ou API padrão do Cosmos.
3. Configure detalhes como:
   - Localização geográfica para disponibilidade.
   - Capacidade (baseada em throughput escalável).
4. Clique em **Criar**.

----------------------------------------------------------------------------------------------------------------------------------

### **Configurando Armazenamento no Azure**
Azure Storage oferece diferentes opções para atender a necessidades específicas.

#### **Exemplo: Criando uma Conta de Armazenamento**
1. No portal, vá para **Todos os Serviços > Armazenamento > Contas de Armazenamento**.
2. Clique em **+ Criar** e defina:
   - **Nome**: Nome único para a conta.
   - **Modelo de Implantação**: Geralmente **Resource Manager**.
   - **Tipo de Conta**: Geral v2 (mais flexível e com suporte a várias opções).
   - **Replicação**: Escolha entre:
     - LRS (Local Redundant Storage)
     - GRS (Geo-Redundant Storage)
3. Depois de configurado, você pode criar **Blobs**, **File Shares**, **Queues** e **Tables**.

#### **Blobs (Armazenamento de Objetos)**
- Ideal para armazenar grandes quantidades de dados não estruturados.
- Use ferramentas como o **Azure Storage Explorer** para gerenciar os dados.

--------------------------------------------------------------------------------------------------------------------------------

### **Recursos Adicionais**
- **Ferramentas CLI e SDKs**: Use o **Azure CLI**, PowerShell ou SDKs para automatizar a criação e o gerenciamento de recursos.
- **Tutoriais e Exemplos**: Acesse a [Central de Tutoriais do Azure](https://learn.microsoft.com/pt-br/azure) para guias passo a passo.
- **Custos e Planejamento**: Use a [Calculadora de Preços do Azure](https://azure.microsoft.com/pt-br/pricing/calculator/) para estimar os custos.