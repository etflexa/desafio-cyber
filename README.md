# Investigação Forense de Logs e Inteligência de Ameaças (Focus Tecnologia)

**Autor:** Eduardo Teixeira Flexa  
**Data:** 29/09/2026

## Objetivo

O desafio teve como objetivo analisar registros de acesso de um servidor, identificar atividades suspeitas, decodificar informações ocultas e investigar a origem de endereços IP.

## Ferramentas utilizadas

- Windows PowerShell
- CyberChef
- VirusTotal

## Resolução

### 1. Análise do log

O arquivo `access.log` foi analisado utilizando o seguinte comando:

```powershell
Select-String -Pattern "==" -Path .\access.log
```

A busca identificou uma requisição suspeita contendo uma sequência codificada em Base64.

**IP identificado:**

```text
212.14.17.145
```

### 2. Decodificação da flag

A sequência encontrada no log foi processada no CyberChef utilizando a operação `From Base64`.

**Resultado:**

```text
THM{CYBERCHEF_WIZARD}
```

### 3. Investigação do IP

O IP `54.36.115.221`, responsável pela tentativa de acesso ao arquivo `.env`, foi consultado no VirusTotal.

**Resultado:**

- **País:** França
- **Empresa:** OVH SAS
- **ASN:** AS16276

### 4. Decodificação do arquivo secreto

O conteúdo do arquivo `encodedflag.txt` foi exibido no PowerShell:

```powershell
Get-Content .\encodedflag.txt
```

Em seguida, o conteúdo foi processado no CyberChef utilizando as operações indicadas no desafio.

A mensagem secreta foi decodificada com sucesso.

## Resumo dos resultados

1. **IP da requisição com Base64:** `212.14.17.145`
2. **Flag decodificada:** `THM{CYBERCHEF_WIZARD}`
3. **Origem do IP `54.36.115.221`:** França, OVH SAS
4. **Arquivo `encodedflag.txt`:** mensagem secreta decodificada com sucesso

## Conclusão

Todos os desafios foram concluídos com sucesso. A atividade permitiu praticar análise de logs, filtragem de registros pelo terminal, decodificação de dados com o CyberChef e investigação de endereços IP com o VirusTotal.
