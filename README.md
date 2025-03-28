# Projeto de Cálculo de IMC - Android

## 📋 Descrição Geral do Projeto  
O aplicativo **Calculadora de IMC** foi desenvolvido para Android com o objetivo de calcular o Índice de Massa Corporal (IMC) de usuários e classificá-los em diferentes categorias (abaixo do peso, normal, sobrepeso, etc.). O app exibe os resultados em telas específicas para cada classificação, com informações personalizadas, incluindo peso, altura, IMC. 

**Principais Funcionalidades:**  
- Cálculo automático do IMC.  
- Navegação para telas específicas conforme a classificação.  
- Exibição de imagens e textos dinâmicos baseados no resultado.  
- Validação de entrada de dados.  
- Interface intuitiva e facil de entender.

---

## 👤 Informações do Aluno  
**Nome:** Israel Ribeiro Ramos  
**RA:** 24026181  
**Disciplina:** Desenvolvimento Mobile 
**Instituição:** FECAP  

---

## 🛠️ Processo de Desenvolvimento  

### **Desafios e Decisões Técnicas**  

#### 1. **Gerenciamento de Múltiplos Layouts**  
- **Problema:** Criar 6 layouts consistentes, mas com elementos únicos (título, imagem).  
- **Solução:** Reutilização de um `ConstraintLayout` base e personalização via XML para cada classificação.  

#### 2. **Atualização Dinâmica do Título**  
- **Problema:** Exibir dados do usuário (peso, altura) dinamicamente.  
- **Solução:** Classe `AlteradorDeTitulo` com formatação via `String.format()`.  

#### 3. **Navegação Baseada em IMC**  
- **Problema:** Direcionar o usuário para a Activity correta.  
- **Solução:** Uso de `Intents` e mapeamento de faixas de IMC para classes específicas (ex: `AbaixoPesoActivity`).  

#### 4. **Reutilização de Código**  
- **Problema:** Evitar repetição em 6 Activities.  
- **Solução:** Classe base `BaseIMCActivity` para herdar lógica comum.  

#### 5. **Internacionalização**  
- **Problema:** Traduzir classificações de IMC de forma amigável.  
- **Solução:** Strings em `res/values/strings.xml` e recuperação dinâmica com `getIdentifier()`.  

#### 6. **Validação de Entrada**  
- **Problema:** Campos vazios ou inválidos.  
- **Solução:** Verificação `isEmpty()` e `Toast` para feedback.  

#### 7. **Compatibilidade e Acessibilidade**  
- **Problema:** Funcionamento em diferentes dispositivos e acessibilidade.  
- **Solução:**  
  - Uso de `AndroidX` para compatibilidade.  
  - `contentDescription` em imagens e foco em elementos interativos.  

#### 8. **Gestão de Estado**  
- **Problema:** Preservar dados durante interrupções (ex: chamadas).  
- **Solução:** Salvamento de estado com `onSaveInstanceState()`.  

#### 9. **Design Responsivo**  
- **Problema:** Layout em telas variadas.  
- **Solução:** Constraints relativas no `ConstraintLayout` e dimensões em `dp`.  

#### 10. **Controle do Back Stack**  
- **Problema:** Comportamento inconsistente do botão "Voltar".  
- **Solução:** Uso de `finish()` após navegação para resultados.  
