# 🔍 Resultados de Teste Exploratório — KaBuM!

Registro de achados de uma sessão de teste exploratório conduzida no site KaBuM!.

---

## 📋 Charter da Sessão

| Campo | Detalhe |
|------|--------|
| Área | Fluxo de busca, filtros e carrinho |
| Missão | Explorar comportamentos inesperados na busca de produtos, aplicação de filtros e gestão do carrinho de compras |
| Duração | 25 minutos |
| Ambiente | Navegador Chrome • Desktop • Com conta logada |
| Data | 30/03/2026 |
| Tester | Fabiana André |
| Hipóteses iniciais | O total do carrinho pode não atualizar corretamente ao alterar quantidade; filtros combinados podem retornar resultados inconsistentes |

---

## 🧭 Heurísticas Utilizadas

- **CRUD** — testar criação, leitura, atualização e remoção de itens no carrinho  
- **Vazio / Cheio / Limite** — testar campos e listas em estados extremos  
- **Fluxo Interrompido** — testar comportamento ao voltar, recarregar e trocar de aba  

---

## 📝 Observações

### **OBS-001 • Cadastro**

| Campo | Detalhe |
|------|--------|
| Área | Cadastro |
| Heurística | CRUD |
| Ação realizada | Inserir ano de nascimento 19999 |
| Resultado esperado | Exibir mensagem de erro ou impedir a ação |
| Resultado obtido | Aparece a mensagem: *"A data não pode estar no futuro"* |
| Classificação | 🟡 Bug |
| Evidência | Cadastro.png |

---

### **OBS-002 • Cadastro com campo vazio**

| Campo | Detalhe |
|------|--------|
| Área | Cadastro |
| Heurística | Vazio / Cheio / Limite |
| Ação realizada | Realizar cadastro com o campo CPF vazio |
| Resultado esperado | Exibir mensagem de erro ou impedir a ação |
| Resultado obtido | Aparece a mensagem: *"CPF obrigatório"* |
| Classificação | ✅ Funciona como esperado — comportamento positivo |
| Evidência | Cadastro-campo-vazio.png |

---

### **OBS-003 • Filtro de marca e produto com escrita incorreta**

| Campo | Detalhe |
|------|--------|
| Área | Filtros |
| Heurística | CRUD |
| Ação realizada | Buscar "Relgio" e aplicar filtro por marca "Samsug" |
| Resultado esperado | Exibir erro ou não retornar resultados |
| Resultado obtido | O número de resultados ("X produtos encontrados") permanece igual ao da busca com termos corretos |
| Classificação | 🟡 Comportamento estranho |
| Evidência | filtro-marca-produto-incorretos.png |

---

### **OBS-004 • Filtro de produto inexistente**

| Campo | Detalhe |
|------|--------|
| Área | Filtros |
| Heurística | CRUD |
| Ação realizada | Buscar produto inexistente, como "Secador de cabelo" |
| Resultado esperado | Exibir mensagem de erro ou nenhum resultado |
| Resultado obtido | Mensagem: *"Lamentamos, nenhum produto encontrado com esse critério de pesquisa."* |
| Classificação | ✅ Funciona como esperado — comportamento positivo |
| Evidência | filtro-produto-inexistente.png |

---

### **OBS-005 • Aplicação de cupom no carrinho**

| Campo | Detalhe |
|------|--------|
| Área | Carrinho |
| Heurística | CRUD |
| Ação realizada | Aplicar cupom em itens selecionados no carrinho |
| Resultado esperado | Cupom válido aplicado corretamente |
| Resultado obtido | Cupom aplicado com sucesso |
| Classificação | ✅ Funciona como esperado — comportamento positivo |
| Evidência | cupom-itens-selecionados-carrinho.png |

---

### **OBS-006 • Botão "Comprar" com carrinho vazio**

| Campo | Detalhe |
|------|--------|
| Área | Carrinho |
| Heurística | Vazio / Cheio / Limite |
| Ação realizada | Remover todos os itens do carrinho e observar o botão |
| Resultado esperado | Botão "Fechar Pedido" desabilitado ou oculto |
| Resultado obtido | Botão permanece ativo e redireciona para a tela inicial ao clicar |
| Classificação | 🟡 Sugestão de melhoria (UX) |
| Evidência | botao-comprar-carrinho-vazio.png |

---

## 📊 Resumo dos Achados

| Classificação | Quantidade |
|--------------|-----------|
| 🔴 Bug | 1 |
| 🟡 Sugestão de melhoria / comportamento estranho | 2 |
| ✅ Funciona como esperado | 3 |
| **Total** | **6 observações** |

---

## 🔎 Próximos Passos

- OBS-001 possui potencial para ser documentado como **bug report formal**

---

## 🛠 Técnicas Aplicadas

- Teste exploratório com charter estruturado  
- Heurísticas aplicadas:  
  - CRUD  
  - Vazio / Cheio / Limite  
  - Fluxo Interrompido  
