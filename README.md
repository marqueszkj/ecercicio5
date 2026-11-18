# Sistema de Acesso à Conta

## Sobre a solução

O programa foi desenvolvido em linguagem C e simula a autenticação de um usuário em uma conta, como em um caixa eletrônico. O usuário informa o número da conta e a senha, e o programa verifica se os dados estão corretos. São permitidas até **3 tentativas**. Se os dados forem corretos em alguma delas, o acesso é autorizado; se as 3 tentativas forem usadas sem sucesso, o acesso é bloqueado.

### Dados de acesso (para teste)

| Dado | Valor |
|------|-------|
| Número da conta | 12345 |
| Senha | 123 |

Os valores são definidos como constantes no código (`CONTA_CORRETA` e `SENHA_CORRETA`).

### Como funciona

1. O programa pede o número da conta e a senha.
2. A cada rodada, o contador de tentativas aumenta em 1.
3. Se a conta **e** a senha estiverem corretas, a variável `acesso_concedido` passa a valer 1.
4. O laço se repete enquanto houver menos de 3 tentativas e o acesso ainda não tiver sido concedido.
5. Ao final, o programa exibe **"Acesso autorizado."** ou **"Acesso bloqueado."**.

### Recursos utilizados

- Constantes (`const int`) para a conta e a senha corretas
- Variáveis do tipo `int` para os dados digitados, o contador de tentativas e o controle de acesso
- Estrutura de repetição `do...while`, que garante pelo menos uma tentativa
- Estruturas condicionais `if` e `else`
- Operador lógico `&&` para exigir que conta e senha estejam corretas ao mesmo tempo
- `scanf()` para entrada de dados e `printf()` para exibir as mensagens

## Como compilar e executar

```bash
gcc acesso.c -o acesso
./acesso
```

## Exemplos de execução

**Acesso autorizado (acertou na 2ª tentativa):**

```
Digite o número da conta: 12345
Digite a senha: 111
Digite o número da conta: 12345
Digite a senha: 123

Acesso autorizado.
```

**Acesso bloqueado (errou as 3 tentativas):**

```
Digite o número da conta: 11111
Digite a senha: 111
Digite o número da conta: 12345
Digite a senha: 000
Digite o número da conta: 99999
Digite a senha: 123

Acesso bloqueado.
```
