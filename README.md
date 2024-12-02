Fornecedor (FornecedorID, Nome, Telefone, Endereço)
|
1---∞
|
Produto (ProdutoID, Nome, Categoria, Preço, QuantidadeEstoque, FornecedorID)
|
1---∞
|
Movimentação (MovimentaçãoID, Tipo, Data, Quantidade, ProdutoID)
-- Tabela Fornecedor
CREATE TABLE Fornecedor (
    FornecedorID SERIAL PRIMARY KEY,
    Nome VARCHAR(100) NOT NULL,
    Telefone VARCHAR(20),
    Endereço VARCHAR(255)
);

-- Tabela Produto
CREATE TABLE Produto (
    ProdutoID SERIAL PRIMARY KEY,
    Nome VARCHAR(100) NOT NULL,
    Categoria VARCHAR(50),
    Preço DECIMAL(10, 2) NOT NULL,
    QuantidadeEstoque INT NOT NULL,
    FornecedorID INT,
    FOREIGN KEY (FornecedorID) REFERENCES Fornecedor(FornecedorID)
);

-- Tabela Movimentação
CREATE TABLE Movimentação (
    MovimentaçãoID SERIAL PRIMARY KEY,
    Tipo VARCHAR(10) CHECK (Tipo IN ('Entrada', 'Saída')),
    Data TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    Quantidade INT NOT NULL,
    ProdutoID INT,
    FOREIGN KEY (ProdutoID) REFERENCES Produto(ProdutoID)
);
