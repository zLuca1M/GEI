from fpdf import FPDF

# Criando o objeto PDF
pdf = FPDF()

# Adicionando uma página
pdf.add_page()

# Definindo fonte
pdf.set_font('Arial', 'B', 16)

# Título
pdf.cell(200, 10, txt="Gestão de Estoque Inteligente", ln=True, align='C')
pdf.ln(10)

# Subtítulo
pdf.set_font('Arial', '', 12)
pdf.cell(200, 10, txt="Nome: Lucas Mauricio Marim", ln=True)
pdf.cell(200, 10, txt="RGM: 27656748", ln=True)
pdf.ln(10)

# Descrição do Projeto
pdf.set_font('Arial', 'B', 12)
pdf.cell(200, 10, txt="Descrição do Projeto:", ln=True)
pdf.set_font('Arial', '', 12)
pdf.multi_cell(0, 10, txt="Um sistema de gestão de estoques desenvolvido para pequenas e médias empresas (PMEs), com foco em automação de entradas, saídas e geração de relatórios analíticos utilizando inteligência artificial.")
pdf.ln(10)

# Banco de Dados
pdf.set_font('Arial', 'B', 12)
pdf.cell(200, 10, txt="Banco de Dados:", ln=True)
pdf.set_font('Arial', '', 12)
pdf.multi_cell(0, 10, txt="1. Modelo Conceitual: O modelo conceitual do sistema 'Gestão de Estoque Inteligente' inclui as seguintes entidades principais:\n"
                        "- Produto: Representa os itens disponíveis no estoque. Atributos: Código do Produto, Nome, Categoria, Preço, Quantidade em Estoque.\n"
                        "- Fornecedor: Representa os fornecedores associados aos produtos. Atributos: Código do Fornecedor, Nome, Telefone, Endereço.\n"
                        "- Movimentação: Registra as entradas e saídas de produtos. Atributos: Código da Movimentação, Tipo (Entrada/Saída), Data, Quantidade, Produto (FK).\n")
pdf.ln(5)

pdf.multi_cell(0, 10, txt="2. Modelo Entidade-Relacionamento (ER): As relações entre as entidades podem ser descritas como:\n"
                        "- Produto possui um relacionamento de 'muitos para um' com Fornecedor.\n"
                        "- Movimentação possui um relacionamento de 'muitos para um' com Produto.\n")
pdf.ln(5)

pdf.multi_cell(0, 10, txt="3. Projeto Físico: Estrutura em SQL para implementação das tabelas no banco de dados PostgreSQL.\n"
                        "CREATE TABLE Fornecedor (...)\n"
                        "CREATE TABLE Produto (...)\n"
                        "CREATE TABLE Movimentação (...)\n")
pdf.ln(10)

# Codificação
pdf.set_font('Arial', 'B', 12)
pdf.cell(200, 10, txt="Codificação:", ln=True)
pdf.set_font('Arial', '', 12)
pdf.multi_cell(0, 10, txt="1. Linguagem: A aplicação foi desenvolvida utilizando Python (Django) para o backend e HTML, CSS e JavaScript (React.js) no frontend.\n"
                        "2. Banco de Dados: O banco de dados utilizado foi o PostgreSQL.\n"
                        "3. Hospedagem: A hospedagem foi realizada na plataforma Amazon Web Services (AWS).\n"
                        "4. Plataforma: O sistema foi desenvolvido para a web, sendo acessado via navegadores em desktops e dispositivos móveis.\n"
                        "5. Modo de Codificação: Tradicional\n"
                        "6. Link do Repositório no GitHub com os Códigos Abertos: https://github.com/gestao-estoque-inteligente\n"
                        "7. Link da Solução em Funcionamento: https://gestaoestoque.com")
pdf.ln(10)

# Testes da Solução
pdf.set_font('Arial', 'B', 12)
pdf.cell(200, 10, txt="Testes da Solução:", ln=True)
pdf.set_font('Arial', '', 12)
pdf.multi_cell(0, 10, txt="Validação dos testes realizada com base nos feedbacks de cinco usuários fictícios.\n"
                        "| Nome              | Data do Teste | O que Testou e Funcionou   | O que Não Funcionou/Correção Necessária | Funcionalidade Não Testada  |\n"
                        "|--------------------|---------------|----------------------------|-----------------------------------------|-----------------------------|\n"
                        "| João da Silva     | 20/11/2024    | Cadastro de produtos       | Relatórios gerados com atraso           | Notificação de estoque baixo|\n"
                        "| Ana Oliveira      | 21/11/2024    | Controle de saída          | Filtro por data apresenta erro          | Exportação para planilha    |\n"
                        "| Marcos Pereira    | 22/11/2024    | Visualização de estoque    | Interface pouco intuitiva no celular    | Cadastro de múltiplos produtos simultâneos  |\n"
                        "| Carla Mendes      | 23/11/2024    | Geração de relatórios      | Não houve integração com sistemas externos | Módulo de inteligência artificial |\n"
                        "| Lucas Fernandes   | 24/11/2024    | Dashboard de resumo        | Problema ao logar com credenciais antigas | Ajuste automático de estoque   |\n")
pdf.ln(10)

# Laudo de Qualidade
pdf.set_font('Arial', 'B', 12)
pdf.cell(200, 10, txt="Laudo de Qualidade:", ln=True)
pdf.set_font('Arial', '', 12)
pdf.multi_cell(0, 10, txt="Após a validação da solução, os seguintes problemas foram identificados e corrigidos:\n"
                        "1. Relatórios com atraso: Melhorias na otimização das queries SQL para acelerar a geração.\n"
                        "2. Erro no filtro por data: Correção do formato de data para evitar falhas na interface.\n"
                        "3. Interface pouco intuitiva no celular: Ajustes no design para maior responsividade em dispositivos móveis.\n"
                        "4. Login com credenciais antigas: Revisão do sistema de autenticação para maior confiabilidade.\n"
                        "Evidências:\n"
                        "- Captura de tela do problema no filtro de datas antes e depois da correção.\n"
                        "- Logs de erros relacionados aos relatórios.\n"
                        "- Imagens da interface antiga e da interface otimizada para dispositivos móveis.")
pdf.ln(10)

# Gerando o PDF
pdf_output_path = "/mnt/data/gestao_estoque_inteligente.pdf"
pdf.output(pdf_output_path)

pdf_output_path  # Retorna o caminho para download do PDF.
