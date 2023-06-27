# Documentação do Ransomware Troll

Esta documentação fornece informações sobre o Ransomware Troll, um programa de criptografia de arquivos malicioso, e mostra como descriptografar arquivos que foram afetados por ele. Este documento inclui uma descrição do código base necessário para descriptografar os arquivos criptografados pelo Ransomware Troll.

## Descrição

O Ransomware Troll é um tipo de malware que criptografa arquivos presentes em um sistema e exige um resgate para fornecer a chave de descriptografia. O código apresentado aqui é uma solução para descriptografar arquivos afetados pelo Ransomware Troll, usando a biblioteca `pyaes` para realizar a descriptografia.

## Pré-requisitos

Antes de executar o código de descriptografia, é necessário ter o Python instalado em seu sistema. Além disso, você deve ter a biblioteca `pyaes` instalada. Você pode instalá-la usando o comando `pip install pyaes`.

## Código Base

Aqui está o código base que pode ser usado para descriptografar arquivos criptografados pelo Ransomware Troll:

```python
import os
import pyaes

## abrir o arquivo criptografado
file_name = "arquivo.txt.ransomwaretroll"
file = open(file_name, "rb")
file_data = file.read()
file.close()

## chave para descriptografia
key = b"testeransomwares"
aes = pyaes.AESModeOfOperationCTR(key)
decrypt_data = aes.decrypt(file_data)

## remover o arquivo criptografado
os.remove(file_name)

## criar o arquivo descriptografado
new_file = "arquivo.txt"
new_file = open(f'{new_file}', "wb")
new_file.write(decrypt_data)
new_file.close()
```

Certifique-se de substituir `"arquivo.txt.ransomwaretroll"` pelo nome do arquivo criptografado real que você deseja descriptografar e `"testeransomwares"` pela chave correta de descriptografia fornecida pelo atacante.

## Instruções

Para descriptografar um arquivo afetado pelo Ransomware Troll, siga estas etapas:

1. Certifique-se de ter instalado o Python em seu sistema.

2. Instale a biblioteca `pyaes` usando o comando `pip install pyaes`.

3. Copie o código base fornecido acima e cole-o em um novo arquivo Python.

4. Abra o arquivo Python em um editor de texto e modifique a linha `file_name = "arquivo.txt.ransomwaretroll"` para corresponder ao nome do arquivo criptografado que você deseja descriptografar.

5. Verifique se a chave correta de descriptografia está definida na linha `key = b"testeransomwares"`. Se o atacante tiver fornecido uma chave diferente, atualize-a aqui.

6. Salve o arquivo Python com um nome adequado, por exemplo, `descriptografar.py`.

7. Abra o terminal ou prompt de comando e navegue até o diretório onde você salvou o arquivo Python.

8. Execute o arquivo Python digitando o seguinte comando: `python descriptografar.py`.

9. O código descriptografará o arquivo e removerá o arquivo criptografado original.

10. Verifique se o arquivo descriptografado foi criado corretamente.

**Nota:** É importante ressaltar que esta solução foi fornecida apenas para fins educacionais

 e de pesquisa, e não é incentivado o uso de ransomware ou atividades ilegais. A descriptografia de arquivos criptografados por ransomware só é possível se você tiver acesso à chave correta de descriptografia. Recomenda-se que você procure assistência de profissionais de segurança cibernética ao lidar com ataques de ransomware.
