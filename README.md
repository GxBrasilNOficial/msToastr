# msToastr
> Permite a utilização da biblioteca [toastr](https://codeseven.github.io/toastr/) dentro do [Genexus](https://www.genexus.com/pt/). 

msToastr é um Objeto User Control [Genexus](https://www.genexus.com/pt/) que permite a criação de mensagens não bloqueantes.


## Importante
Esta versão utiliza um [External Object](https://wiki.genexus.com/commwiki/servlet/wiki?31064,External+Objects+for+Javascript#:~:text=By%20the%20means%20of%20an,resources%20in%20a%20smooth%20way.) portanto não substitui as mensagens nativas ([Msg](https://wiki.genexus.com/commwiki/servlet/wiki?31635,Msg+function) e [Error](https://wiki.genexus.com/commwiki/servlet/wiki?6852,Error+rule)).

## Diferencial
Permite a passagem direta do datatype [Messages](https://wiki.genexus.com/commwiki/servlet/wiki?40335,Messages+structured+data+type) do [Genexus](https://www.genexus.com/pt/), com isso o próprio User Control irá verificar o tipo de Toast que deve ser exibido.

## Notas
A sintaxe utilizada no Objeto UC está em um nível de otimização superior em relação ao UC [msMediaQuery](https://github.com/GxBrasilNOficial/msMediaQuery), mas ainda escrito afim de facilitar a compreensão daqueles que não desenvolvem em JavaScript.


## Instalação

Genexus 16 ou Superior:

```Oxygene
1 - Na IDE Genexus, navegue em Knowledge Manager / Import.
2 - Selecione o Arquivo msMediaQuery.xml ** Note que é preciso alterar o filtro da caixa de seleção para XML.
** Para geradores Java, verifique o caminho no qual o Objeto File [msToastrJS] esta sendo extraído.
```

## Exemplo de uso

```
Event 'Error'
	
	msToastrAPI.Error('isso é erro')
	
Endevent

Event 'Warning'
	
	msToastrAPI.Warning('isso é alerta')
	
Endevent

Event 'info'
	
	msToastrAPI.Info('isso é info')
	
Endevent

Event 'Success'
	
	msToastrAPI.Success('isso é sucesso')
	
Endevent

Event 'MessagesGx'
	
	&Messages.Clear()
	
	&Message = New()
	&Message.Id		= 'id1'
	&Message.Description	= 'Isso é um erro direto do Messages'
	&Message.Type		= MessageTypes.Error
	&Messages.Add(&Message)
	
	&Message = New()
	&Message.Id		= 'id2'
	&Message.Description	= 'Isso é um alerta direto do Messages'
	&Message.Type		= MessageTypes.Warning
	&Messages.Add(&Message)
	
	msToastrAPI.MessagesGx(&Messages)
	
Endevent
	
```

## Histórico de lançamentos

* 0.1.0
    * Primeira versão funcional [@gtorrezani](https://github.com/gtorrezani)


## Meta

Gustavo Torrezani Matias – [@instagram](https://www.instagram.com/matiassolucoes/)

A bibliote original é distribuído sob a licença [MIT](https://choosealicense.com/licenses/mit/), sendo assim o UC é distribuído com a mesma licença.
