## Explicação Arquivos Kotlin

### TickerResponse.kt

Neste arquivo temos dois modelos de dados em Kotlin que usam o construtor primário para mapear automaticamente a resposta JSON de um “ticker” em objetos imutáveis.

---

### MercadoBitcoinService.kt

Aqui definimos a interface MercadoBitcoinService, que usa Retrofit para fazer uma requisição HTTP GET assíncrona ao endpoint "api/BTC/ticker/" com suspend fun e retorna um Response<TickerResponse> para facilitar o tratamento da resposta JSON em objetos Kotlin.

---

### MercadoBitcoinServiceFactory.kt

Neste é localizado a MercadoBitcoinServiceFactory, que constrói uma instância Retrofit apontada para https://www.mercadobitcoin.net/, adiciona o conversor Gson para JSON e retorna o serviço MercadoBitcoinService pronto para usar a API.

---

### MainActivity.kt

Aqui informamos que, ao ser criada a MainActivity, configura a interface (Toolbar e botão de atualização), e utiliza um CoroutineScope(Dispatchers.Main) para chamar assincronamente o serviço de ticker via Retrofit e atualizar os TextViews com o valor formatado como moeda e a data formatada.

---

## Evidências

### Abrindo o aplicativo

![Img1](https://github.com/user-attachments/assets/fa6886ac-0840-472d-bcac-cbb7eaa64282)

---

### Clicando para atualizar o valor

![Img2](https://github.com/user-attachments/assets/c5d0556f-03a1-4600-bf21-1bd9d0e5256f)
