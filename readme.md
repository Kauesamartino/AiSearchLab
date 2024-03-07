## Laboratório de Inteligencia de Documentos

### Passo a passo

Para iniciar, crie um recurso no [Azure AI Search](https://portal.azure.com/#view/Microsoft_Azure_Marketplace/GalleryItemDetailsBladeNopdl/id/Microsoft.Search/selectionMode~/false/resourceGroupId//resourceGroupLocation//dontDiscardJourney~/false/selectedMenuId/home/launchingContext~/%7B"galleryItemId"%3A"Microsoft.Search"%2C"source"%3A%5B"GalleryFeaturedMenuItemPart"%2C"VirtualizedTileDetails"%5D%2C"menuItemId"%3A"home"%2C"subMenuItemId"%3A"Search%20results"%2C"telemetryId"%3A"348e212a-9fa4-47b7-b36f-d36c27e56bd4"%7D/searchTelemetryId/48c3d8ee-ea6a-4740-aad3-e4180848b591) com as opções:

- __Assinatura:__ Sua assinatura do Azure
- __Resource Group:__ Crie um grupo ou use um existente, caso desejar
- __Localização:__ East Us (Recomendado devido aos altos valores do Brasil)
- __Nome:__ Um nome intuitivo de sua escolha
- __Pricing Tier:__ Basic (Storage 2tb e 15 indexes)

Após finalizar a criação do recurso __AI Search__, devemos criar um recurso [Azure AI Service](https://portal.azure.com/#create/Microsoft.CognitiveServicesAllInOne), com as opções:

- __Assinatura:__ Sua assinatura do Azure
- __Resource Group:__ Selecione o mesmo Resource Group do AI Search
- __Localização:__ East Us (Recomendado devido aos altos valores do Brasil)
- __Nome:__ Um nome intuitivo de sua escolha
- __Pricing Tier:__ Standard SO
- __Marque a Checkbox__

Após finalizar a criação do recurso, crie uma conta de armazenamento em [Storage Account](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Storage%2FStorageAccounts) com as opções:

- __Assinatura:__ Sua assinatura do Azure
- __Resource Group:__ Selecione o mesmo Resource Group do AI Search
- __Localização:__ East Us (Recomendado devido aos altos valores do Brasil)
- __Nome:__ Um nome intuitivo de sua escolha (O nome deve ser único)
- __Performance:__ Standard SO 
- __Redundancy:__ Locally-redundant storage (LRS)
- __Marque a Checkbox__

Após finalizar a criação do Storage, entre no Storage Account criado, e vá na opção Configuration e certifique-se de que o Acesso Anonimo de Blob esteja permitido, caso esteja desabilitado, habilite. 
Assim que finalizado, vá para o __Containers__ e adicione um novo container, com o nome __coffeereviews__ e o level de acesso __Container__. Finalizado a criação do containter, acesse e baixe o [Arquivo para Upload](https://aka.ms/mslearn-coffee-reviews) do container.   
Após baixar o arquivo, selecione a opção __Upload__ do container e importe esse arquivo baixado, e assim finalizara os passos necessarios para o storage e deverá ir para o __Ai Search__ que você criou.  

No Azure Ai Search, vá para a opção __Import Data__ e dentro dela selecione o local dos dados cognitivos (__coffeereviews__). Então a base de pesquisa ja estará funcionando e devemos ir para __Search Explorer__.

Na barra de pesquisa, para saber se a cadeia de pesquisa está funcionando, digite o código:
__search=*&$count=true__

Caso esteja, então podemos começar a pesquisar, utilizando palavras chaves como no código a seguir:
__search=locations:'Chicago'__

Assim o recurso retornará dados de vendas do Café de Chicago, possibilitando analises de sentimento dos clientes do café.