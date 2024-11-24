## Configuração de uma instância de banco de dados no Azure com armazenamento e autenticação.

--------------------------------------------------------------------------------------------------------------------------

### **Criando uma Instância de Banco de Dados no Azure**

#### **Passos Básicos:**
1. **Acesse o portal do Azure:**
   - Entre no [Portal do Azure](https://portal.azure.com).

2. **Navegue até os serviços de banco de dados:**
   - Vá para **Todos os Serviços > Bancos de Dados > Azure SQL**.

3. **Clique em “+ Criar”**:
   - Escolha **Banco de Dados Único** para uma instância autônoma.
   - Outra opção é criar um **Pool Elástico** ou uma **Instância Gerenciada**, dependendo da sua necessidade.

4. **Configurações Básicas**:
   - **Nome do Banco**: Escolha um nome único.
   - **Servidor SQL**: 
     - Crie um servidor ou use um existente.
     - Defina o nome do servidor, região e credenciais de administrador.
   - **Modelo de Compra**:
     - **Baseado em vCore** (alto desempenho) ou **DTU** (soluções mais simples e econômicas).
   - Escolha a **camada de serviço**: 
     - Básica, Padrão ou Premium, dependendo do desempenho necessário.

5. **Armazenamento**:
   - Defina o tamanho máximo do banco de dados (de 5 GB a 4 TB, dependendo do plano).
   - Escolha o tipo de armazenamento:
     - **SSD Premium**: Melhor para alto desempenho.
     - **SSD Standard** ou **Armazenamento Geral**: Para cargas de trabalho moderadas.

6. **Revisar e Criar**:
   - Após configurar, clique em **Revisar + Criar** e aguarde a implantação.

---------------------------------------------------------------------------------------------------------------------

### **Configurando Armazenamento**

O armazenamento no Azure SQL é ajustável e integrado ao desempenho do banco de dados.

- **Ajustar Espaço e Performance**:
  - Durante a criação ou depois, você pode aumentar o tamanho do banco para escalar automaticamente.
  - Usar "Auto-Scale" permite ajustar o desempenho e o espaço conforme a demanda.

- **Backups e Restauração**:
  - O Azure SQL automaticamente realiza backups regulares.
  - Configure o **Retention Period** (7 a 35 dias para restauração de backups automáticos).

----------------------------------------------------------------------------------------------------------------------

### **Configurando Autenticação**

O Azure SQL suporta dois métodos principais de autenticação:

#### **3.1 Autenticação do SQL Server (Tradicional)**
- Ao configurar o servidor, você define um **nome de administrador** e uma **senha**.
- Essa autenticação usa **credenciais fixas** para acessar o banco.

#### **3.2 Autenticação do Azure Active Directory (AAD)**
- **Benefícios**:
  - Permite gerenciar permissões usando identidades centralizadas no Azure AD.
  - Suporte a MFA (Autenticação Multifator) para maior segurança.
- **Configuração**:
  1. Acesse o servidor SQL criado no portal.
  2. Vá para a guia **Configurações > Identidade do Azure Active Directory**.
  3. Configure um administrador do Azure AD:
     - Escolha um grupo ou usuário já cadastrado no Azure AD.
  4. Salve e atualize.

#### **3.3 Autenticação Híbrida**
- Combinação dos dois métodos (SQL Server + Azure AD).
- Útil para compatibilidade e transição de sistemas antigos para novas práticas.

--------------------------------------------------------------------------------------------------------------------

### **Configurando Regras de Rede e Firewall**

1. **Acessando Configurações de Rede:**
   - Navegue até **Servidor SQL > Segurança > Firewall e Rede Virtual**.

2. **Permitir Acesso por IP:**
   - Adicione o endereço IP do cliente na lista de permissões para conexões externas.
   - Alternativamente, configure uma **Rede Virtual (VNet)** para comunicação privada.

3. **Ativando Segurança Avançada**:
   - Habilite o **Azure Defender para SQL** para proteger contra ameaças em tempo real.
   - Use regras de firewall para bloquear portas e restringir acessos.

-------------------------------------------------------------------------------------------------------------------------

### **Conectando-se ao Banco de Dados**

Após configurar a instância e a autenticação, você pode conectar-se ao banco:

1. **Usando Azure Data Studio ou SQL Server Management Studio (SSMS):**
   - Forneça as credenciais configuradas (SQL ou Azure AD).
   - Use o nome do servidor no formato: `servername.database.windows.net`.

2. **Usando Strings de Conexão:**
   - O Azure fornece strings de conexão pré-configuradas para .NET, JDBC, PHP, etc.
   - ADO.NET:
     ```csharp
     "Server=tcp:servername.database.windows.net,1433;Initial Catalog=dbname;Persist Security Info=False;User ID=admin;Password=yourpassword;MultipleActiveResultSets=False;Encrypt=True;TrustServerCertificate=False;Connection Timeout=30;"
     ```

----------------------------------------------------------------------------------------------------------------------------

### **Monitoramento e Escalabilidade**

- **Monitoramento**:
  - Use o **Azure Monitor** para verificar métricas como desempenho, consultas lentas e consumo de armazenamento.
  - Ative alertas para thresholds críticos (por exemplo, uso de CPU acima de 80%).

- **Escalabilidade**:
  - Ajuste o tamanho do banco ou a camada de serviço conforme necessário.
  - Use o **Auto-Scale** para gerenciar custos e evitar interrupções.

-----------------------------------------------------------------------------------------------------------------------

### **Benefícios dessa Configuração**

- **Alta Segurança**: Suporte a autenticação multifator (MFA) e proteção avançada.
- **Desempenho Otimizado**: Escalabilidade fácil para gerenciar cargas de trabalho dinâmicas.
- **Backup e Recuperação**: Backups automáticos garantem recuperação em casos de falhas.
- **Conformidade**: Recursos integrados para atender a padrões como GDPR, HIPAA, etc.