---
title: Teste de planejamento e gerenciamento com planos de teste do Azure 
layout: page
sidebar: vsts
permalink: /labs/azuredevops/testmanagement/
folder: /labs/azuredevops/testmanagement/
version: Lab version - 15.8.2
updated: Última Atualização - 9/6/2018
redirect_from: "/labs/vsts/testmanagement/index.htm"
---
<div class="rw-ui-container"></div>
<a name="Overview"></a>

## Visão geral ##

Neste laboratório, você aprenderá a usar o Azure DevOps para gerenciar o ciclo de vida dos testes do projeto. Este projeto irá guiá-lo através da criação de planos de teste projetados para validar eficientemente seus marcos de software. Você também criará e executará testes manuais que podem ser consistentemente reproduzidos ao longo de cada lançamento.

<a name="Prerequisites"></a>
### Pré-requisitos. ###

- Este laboratório requer que você complete as tarefas 1 e 2 do <a href="../prereq/">pré-requisito</a> instruções.

<a name="Exercise1"></a>
## Exercício 1: Gerenciando planos de teste, suites e casos ##

Neste exercício, você aprenderá como criar e gerenciar planos de teste, testes de teste e casos de teste.

<a name="Ex1Task1"></a>
### Tarefa 1: Entendendo planos de teste, suítes e casos ###

1. Navegue até o seu projeto de equipe sobre o Azure DevOps.

1. Selecione **Test Plans** para navegar até o **Test Hub**. O Hub de teste fornece um local central para todos os planejamentos, execução e análise de teste.

    ![](images/000.png)

1. Em geral, todo marco importante em um projeto deve ter o seu próprio **plano de teste**. Dentro de cada plano de teste temos **suites de teste** , que são coleções de **casos de teste** (e opcionalmente outras suítes de teste) projetadas para validar um item de trabalho, como uma implementação de recursos ou correção de bugs. Cada caso de teste é projetado para confirmar um comportamento específico e pode pertencer a uma ou mais suítes de teste. O projeto ilimitado de peças tem um plano de teste, que está sob o **Parts Unlimited Team** e sob **Parts Unlimited_TestPlan1**. Selecione o **Parts Unlimited_TestPlan1** plano de teste.

    ![](images/001.png)

1. Selecione o conjunto de testes para a história **As a customer, I would like to store my credit card details securely**. Este conjunto de testes se concentra nesse item de trabalho, que acontece com um recurso. Observe que os id dos itens de trabalho variam toda vez que você gerar dados de demonstração para um laboratório.

    ![](images/002.png)

1. No lado direito, você pode ver que este conjunto de testes possui três casos de teste projetados para confirmar o comportamento esperado da implementação do recurso. Clique duas vezes no caso de teste **Verify that user is allowed to save his credit card detail**.

    ![](images/003.png)

1. Esta caixa de diálogo fornece todas as informações que você precisa neste caso de teste. Localize o painel **Related Work** e note que este caso de teste está ligado ao suíte que pertence. Clique no item de trabalho para navegar até ele.

    ![](images/004.png)

1. No conjunto de testes, podemos ver todos os itens de trabalho vinculados, que são os casos de teste.

    ![](images/005.png)

1. No entanto, ainda não está associado ao recurso que ele foi projetado para testar, que podemos vincular agora. Clique **Add link \| Existing item**.

    ![](images/006.png)

1. Colocou o **Link type** para **Parent** e procure pelo **"credit card"**.

    ![](images/007.png)

1. Selecione a **Funcionalidade** com **Credit Card Purchase**.

    ![](images/008.png)

1. Clique **OK**.

    ![](images/009.png)

1. O recurso pai agora está associado à suíte que o teste e qualquer pessoa pode navegar entre eles para visualizar seu relacionamento em relação aos outros itens de trabalho envolvidos.

    ![](images/010.png)

1. Clique em **Salvar & fechar**.

    ![](images/011.png)

1. Feche a caixa de diálogo de caso de teste original.

<a name="Ex1Task2"></a>
### Tarefa 2: Gerenciando testes ###

1. Às vezes, um conjunto de casos de teste deve ser executado em uma ordem específica para maximizar a eficiência. Clique em **ordem de testes** Para especificar a ordem, esses casos de teste devem ser executados.

    ![](images/012.png)

1. Embora estes casos de teste pudessem ser executados separadamente para confirmar o comportamento, provavelmente faz mais sentido executar o caso de teste que rejeita cartões inválidos primeiro. Em seguida, o testador pode confirmar que um cartão válido pode ser salvo, seguido pelo caso de teste para editar um cartão salvo. Arraste e solte o segundo caso de teste acima do primeiro e clique em **Feito**.

    ![](images/013.png)

1. Agora você pode ver que a **ordem** foi atualizado e que a lista agora é classificada por ela.

    ![](images/014.png)

1. Outro aspecto significativo de testes tem a ver com o ambiente em que cada teste é executado. Para este aplicativo da Web, o navegador e o sistema operacional são as principais considerações. Agora todos os testes usam apenas uma configuração: Windows 10.

    ![](images/015.png)

1. Selecione a aba de **Configurações.**.

    ![](images/016.png)

1. Note que há uma configuração existente para **Windows 10.**. Cada configuração de teste inclui um nome e uma descrição, bem como um conjunto de **Variáveis de configuração.**. Este projeto tem um conjunto de variáveis de configuração chamado **Operating System**. Você pode facilmente adicionar mais e / ou editar as entradas disponíveis para cada um. Clique **Adicione variável de configuração**.

    ![](images/017.png)

1. Selecione a variável **Browser** e configurá-lo para **Microsoft Edge**.

    ![](images/018.png)

1. Clique em **Salvar** para salvar a configuração.

    ![](images/019.png)

1. Agora vamos supor que a equipe de teste tenha adquirido um iPhone X e quiser adicioná-lo na matriz de teste. É muito fácil registrar este ambiente como uma nova configuração para que os casos de teste possam especificá-lo. No entanto, antes de adicioná-lo, precisaremos de um **Operating System** para **iOS 10.**. Clique na variável **Operating System**.

    ![](images/020.png)

1. Clique em **Adicionar novo valor** e adicione uma entrada para **iOS 12.**.

    ![](images/021.png)

1. Clique **Salvar**.

    ![](images/022.png)

1. Agora temos tudo o que precisamos para adicionar o iPhone X. Clique no dropdown **Adicionar** e selecione **Nova configuração de teste**.

    ![](images/023.png)

1. Defina o **Nome** para **"iPhone X"**.

    ![](images/024.png)

1. Clique em **Adicione variável de configuração** duas vezes e defina **Browser** para **Safári** e **Operating System** para **iOS 12.**.

    ![](images/025.png)

1. Clique **Salvar** para salvar a nova configuração.

    ![](images/026.png)

1. Retorne para a aba **Planos de teste**.

    ![](images/027.png)

1. Clique na lista suspensa ao lado do pacote de teste que temos trabalhado até agora e selecione **Atribuir configurações para a suite de teste**.

    ![](images/028.png)

1. Selecione o **iPhone X** e clique **Salvar**.

    ![](images/029.png)

1. Observe que cada caso de teste foi duplicado com uma configuração adicional para **iPhone X.**. Agora cada ambiente pode ser testado e rastreado separadamente.

    ![](images/030.png)

<a name="Ex1Task3"></a>
### Tarefa 3: Criação de caso de testes ###

1. Expanda a lista suspensa ao lado do plano de teste e selecione **Nova suíte estática**. Uma  **Suite estática** de casos de teste é uma suíte onde os casos foram atribuídos manualmente. Você também pode criar suítes com base em requisitos comuns ( **Suíte baseada em requisitos** ) ou uma consulta de casos de teste e / ou itens de trabalho ( **Suíte baseada em consulta** ).

    ![](images/031.png)

1. Defina o nome do novo suíte para **"Testes de envio"**. Esses testes se concentrarão na funcionalidade relacionada ao envio. Lembre-se de que você pode compartilhar facilmente os casos de teste em todas as suites, portanto, há redundância mínima ao ter muitas suítes sobrepostas.

    ![](images/032.png)

1. Expanda a lista suspensa ao lado do suíte recém-criado e selecione **Novo Suíte Baseado em Requisitos**.

    ![](images/033.png)

1. Você poderia personalizar a consulta usada para especificar quais requisitos são recuperados, mas apenas deixe os padrões e clique em **Executar consulta**. Localize e selecione os três itens Backlog do produto relacionados a "**shipping**". Clique **Criar suítes.** para criar um conjunto de testes para cada um.

    ![](images/034.png)

1. Selecione uma das suítes recém-criadas, como a associada ao status do pacote de rastreamento.

    ![](images/035.png)

1. Enquanto você pode criar casos de teste um de cada vez, às vezes é mais fácil usar um layout de grade para adicionar rapidamente muitos casos de teste. No painel de casos de teste, selecione **Nova\|Novo caso de teste usando grade**.

    ![](images/036.png)

1. Digite alguns casos de teste e clique no botão **Salvar tudo**. O **Título** será o eventual título do caso de teste. **Ação de passo** será o primeiro (e possivelmente a única) etapa do teste. Se esse passo tiver um resultado esperado, você pode especificá-lo como **Resultado esperado**.

    ![](images/037.png)

1. Você pode, opcionalmente, continuar adicionando e editar itens de trabalho na exibição da grade. Quando satisfeito, volte para a visualização da lista clicando no botão **Ver: Grade.**.

    ![](images/038.png)

1. A visualização da lista mostra os mesmos dados, mas em uma exibição diferente.

    ![](images/039.png)

1. Outra opção para criar suítes é via consulta de item de trabalho. Expanda a lista suspensa ao lado da suite **Shipping Tests** e selecione **Nova suíte baseada em consulta**.

    ![](images/040.png)

1. Digamos que você queira criar uma suíte de teste de casos de teste relacionados ao envio no projeto. Mudar o **Tipo de item de trabalho** para **Microsoft.TestCaseCategory** para procurar casos de teste e clique em **Executar consulta**. Agora você tem uma lista de casos de teste que você pode selecionar para criar suítes, se você escolher.

    ![](images/041-2.png)

1. Pressione **Esc** para fechar a caixa de diálogo.

<a name="Exercise2"></a>
## Exercício 2: Criação, executando e analisando testes manuais ##

Neste exercício, você aprenderá como criar um plano de teste manual e preenche-lo com etapas. O plano pode posteriormente ser executado para confirmar o comportamento esperado do seu software. Neste laboratório, vamos nos concentrar em criar um novo caso de teste manual e executá-lo.

<a name="Ex2Task1"></a>
### Tarefa 1: Instalando a extensão de teste e feedback ###

1. Instalar **Google Chrome** a partir de [http://google.com/chrome.](http://google.com/chrome). O resto deste exercício usará o Chrome como seu navegador. Se você já estiver usando o Chrome, basta abrir uma nova instância para o próximo conjunto de etapas.

1. Navegue até o **Marketplace do Azure Devops.** no [http://marketplace.visualstudio.com.](http://marketplace.visualstudio.com/).

1. Selecione a aba **Azure DevOps.**. Procurar por "**feedback**" e clique na extensão **Test & feedback**.

    ![](images/042.png)

1. Clique em **Instalar** na página de detalhes.

    ![](images/043.png)

1. Clique em **Instalar** para a extensão do Chrome.

    ![](images/044.png)

1. Na **Loja online do Chrome**, clique em **Adicionar ao Chrome**.

    ![](images/045.png)

1. Confirme a instalação quando solicitado.

    ![](images/046.png)

1. Para abrir a extensão, clique no ícone de extensão que aparecerá à direita da barra de endereços. Selecione a aba **Configurações de conexão**. Digite o URL da sua instância do Azure DevOps, como "**[https://myteam.visualstudio.com.](https://MYTEAM.visualstudio.com)**", no campo **Server URL** e clique em **Next**.

    ![](images/047.png)

1. A extensão pode ser usada em dois modos: **Connected** e **Standalone**. Se você tiver o Azure DevOps ou o Team Foundation Server (TFS), selecione o modo conectado. O modo autônomo é para usuários que não têm o Azure DevOps ou TFS e desejam usar a extensão para arquivar erros e compartilhar o relatório com sua equipe.

1. Depois de se conectar ao Azure DevOps, você precisará selecionar a equipe que deseja que esses esforços associados. Selecione o time ****Parts Unlimited Team**** debaixo de ****Parts Unlimited**** e clique em **Save** para continuar.

    ![](images/048.png)

<a name="Ex2Task2"></a>
### Tarefa 2: Criacao de um plano de teste manual ###

1. No Chrome, navegue até o seu  projeto **Parts Unlimited**

1. Como antes, navegue até o hub **Planos de teste**.

    ![](images/049.png)

1. Expanda a lista suspensa ao lado do plano de teste e selecione **Nova suíte estática**.

    ![](images/050.png)

1. Nomeie o novo suíte **"Testes de ponta a ponta"** e pressione. **Entrar**.

    ![](images/051.png)

1. De **Testes.** Tab, selecione. **Nova\|Novo caso de teste** para criar um novo caso de teste.

    ![](images/052.png)

1. No **Título** caixa, digite "**Confirm that order number appears after successful order**" como o nome do novo caso de teste.

    ![](images/053.png)

1. Neste ponto, estamos prontos para adicionar etapas para este teste manual. Cada etapa inclui uma **Açao** , que descreve a ação que o testador precisa executar. Opcionalmente, uma etapa pode incluir um **resultado esperado** , que descreve o resultado esperado da ação dada. No painel de **Passos**, crie um passo para cada uma das seguintes **Ações**  abaixo , das quais apenas uma tem um **resultado esperado**.


    |Ação|Resultado esperado|
    --- | ---
    |Abrir site do projeto||
    |Clique em **Brakes**||
    |Clique em **Disk and Pad Combo**||
    |Clique **Add to Cart**||
    |Clique **Checkout**||
    |Digite @Email, @Password||
    |Digite @Name, @Phone, @Email, @Address, @City, @State, @PostalCode, @Country, @Promo||
    |Clique em **Submit Order**||
    |Confirme que a páginas de ordens tem uma ordem #|**Order** # deve aparecer uma tela de confirmação de ordem|
    |Log out||
    |Feche o navegador||

**Observação:** Se você acabar com um passo extra vazio, exclua-o.

1. Neste ponto, o painel de **passos** deve parecer semelhante ao seguinte:

    ![](images/054.png)

1. Observe os passos "Digite @Email, @Password" e "Digite @name, @Phone, @Email, @address, @City, @state, @Postalcode, @Country, @promo". Nestes passos, usamos o sinal **@ ** para indicar que havia variáveis específicas de iteração a serem usadas durante o passe de teste manual. Podemos definir quais variáveis usar rolando para a seção de **Valores de parâmetros** deste formulário e entrando nelas para cada iteração. Observe que você pode precisar usar a barra de rolagem no lado direito da caixa de diálogo de caso de teste para visualizar esta seção.

    ![](images/055.png)

1. Use a tabela a seguir para configurar valores para duas iterações.

| Campos        | Iteração 1.                             | Iteração 2.                                |
| ------------- | ---------------------------------------- | ------------------------------------------ |
| E-mail        | [admin@test.com.](mailto:admin@test.com) | [sachin@test.com.](mailto:sachin@test.com) |
| Senha         | P @ ssw0rd.                              | P @ ssw0rd.                                |
| Nome          | Usuário de administrador.                | Sachin Raj.                                |
| Telefone      | 425-555-1234.                            | 555-555-5555.                              |
| Endereço      | Uma Microsoft Way.                       | Duas trilha da cauda                       |
| Cidade        | Redmond                                  | Springfield                                |
| Estada        | soma                                     | A                                          |
| Código postal | 98052.                                   | 11135.                                     |
| País          | EUA                                      | EUA                                        |
| Promoção      | FREE                                     | FREE                                        |

1. A seção **Valores de parâmetros** deve agora se parecer com isso. Observe que você pode inserir quantas iterações você precisar para testar totalmente a amplitude do cenário.

    ![](images/056.png)

1. Clique em **Salvar fechar** para salvar o caso de teste.

    ![](images/057.png)

<a name="Ex2Task3"></a>
### Tarefa 3: Executando um plano de teste manual ###

1. Nesta tarefa, você aprenderá como executar o plano de teste manual que criamos anteriormente. Observe que o processo para acionar um teste automatizado segue um fluxo de trabalho semelhante. Você pode aprender mais sobre isso no[documentação](https://docs.microsoft.com/en-us/vsts/build-release/test/run-automated-tests-from-test-hub).

1. Clique com o botão direito do mouse no caso de teste criado anteriormente e selecione **Executar com opções** para começar um teste manual.

    ![](images/058.png)

1. Existem algumas opções que você pode usar para personalizar cada teste. A primeira opção é selecionar um **executor** , que será o navegador neste cenário. Em seguida, você pode ter a opção de especificar quais tipos de **dados para coletar**. Por fim, você pode, opcionalmente, especificar qual build está sendo testado para tornar mais fácil associar os resultados com o build de onde vieram. Clique em **OK** continuar.

    ![](images/059.png)

1. Se a janela de **Test Runner** não aparecer, verifique se foi bloqueado pelo bloqueador pop-up. Em caso afirmativo, clique no **Bloqueador de pop-up** e selecione **Sempre permita pop-ups...** e, em seguida, clique em **Feito**. Você pode então lançar o teste novamente com o sucesso.

1. Na janela de **Test Runner**, expanda o dropdown **Test 1 of 1: Iteration 1**. Observe que existem duas iterações: uma para cada conjunto de parâmetros especificados no caso de teste. Na primeira iteração, a conta [admin@test.com.](mailto:admin@test.com) é usada. No segundo, [sachin@test.com.](mailto:sachin@test.com) será usado.

    ![](images/060.png)

1. O primeiro passo no teste é abrir o site do projeto. Para fazer isso, mude para a instancia do **Visual Studio** que tem a solução **Parts Unlimited** carregada. No dropdown **IIS Express.** selecione **Navegue com...**.

    ![](images/061.png)

1. Selecione **Google Chrome** e clique em **Navegar**.

    ![](images/062.png)

1. Se você estiver trabalhando em uma tela grande, pode ser mais fácil redimensionar a nova janela para se encaixar ao lado da janela do **Test Runner**. Caso contrário, você pode simplesmente mudar para frente.

    ![](images/063.png)

1. Uma vez que o site carregar, retorne ao **Test Runner** e clique no botão **Passe o passo de teste**. Ao preencher os próximos passos deste teste, certifique-se de verificar o botão **Passe o passo de teste** para eles também.

    ![](images/064.png)

1. O próximo passo é clicar no item do menu **Brakes**.

    ![](images/065.png)

1. Em seguida, clique no produto **Disk and Pad Combo**.

    ![](images/066.png)

1. O próximo passo é clicar no botão **Add to Cart**.

    ![](images/067.png)

1. Na próxima página, clique em **Checkout**.

    ![](images/068.png)

1. Faça o login usando as credenciais especificadas na próxima etapa.

    ![](images/069.png)

1. Infelizmente, isso vai falhar porque não há uma conta [admin@test.com.](mailto:admin@test.com).

    ![](images/070.png)

1. O **Test Runner** fornece três maneiras valiosas de registrar evidencias de um teste. A primeira opção é realizar capturas de tela. A segunda é capturar cada ação de usuário em um log de ação de imagem. A final é registrar a tela como um vídeo. Clique no botão de **Captura de tela** para tomar uma captura de tela.

    ![](images/071.png)

1. Cortar a tela para baixo para mostrar o formulário de login e a mensagem de erro. Especifique o nome **"Sem conta de administrador"** e clique no. **confirme** botão.

    ![](images/072.png)

1. Clique com o botão direito do mouse na etapa com falha e selecione **Adicionar comentário**.

    ![](images/073.png)

1. Digite um comentário de **"Conta de administrador não existe por padrão"** e falhe no teste usando o botão de **Passo de teste de falha**.

    ![](images/074.png)

1. Clique em **Criar bug** para registrar um novo bug.

    ![](images/075.png)

1. Digite o título do bug como **"Conta de administrador não existe por padrão"** e clique **Salvar & fechar** para registrar o bug.

    ![](images/076.png)

1. Como o teste não pode ser concluído devido a um bug não diretamente relacionado à funcionalidade sendo testada, expanda o dropdown **Marca de resultado de caso de teste** e selecione. **Bloqueiar teste**. Clique em **Salvar & fechar** para salvar o teste.

    ![](images/077.png)

1. Feche as janelas do navegador de teste.

<a name="Ex2Task4"></a>
### Tarefa 4: Analisando os resultados do teste manual ###

1. Nesta tarefa, você aprenderá como revisar os resultados de um teste manual.

1. Retornar à janela do navegador que hospeda o **HUB DE TESTE**. Selecione a aba **Executar**.

    ![](images/078.png)

1. Clique duas vezes no teste mais recente para abri-lo. Você pode precisar atualizar os dados para vê-lo.

    ![](images/079.png)

1. A guia **Resumo de execução** fornece uma visão geral do teste, bem como detalhes de alto nível sobre os resultados de todos os testes incluídos como parte da execução.

    ![](images/080.png)

1. Selecione a aba **Resultado dos testes**. Esta guia lista os resultados de cada caso de teste individual incluído na corrida junto com seus resultados. Como havia apenas um caso de teste incluído aqui, clique duas vezes para abrir.

    ![](images/081.png)

1. Você pode revisar todos os detalhes para este caso de teste específico daqui.

    ![](images/082.png)

1. Vá até o fundo para localizar as iterações. Expanda a primeira iteração.

    ![](images/083.png)

1. Revise os resultados de cada etapa nesta iteração, bem como a etapa de login com falha, que mostra a captura de tela anexada durante o teste.

    ![](images/084.png)

<a name="Ex2Task5"></a>
### Tarefa 5: Criando etapas compartilhadas ###

1. Nesta tarefa, você aprenderá como criar etapas compartilhadas. Um passo compartilhado combina várias etapas que são comumente executadas em sequência em uma única etapa lógica, que podem ser compartilhadas entre os testes. Se o processo definido pelas etapas compartilhadas sempre alterar no futuro, você poderá atualizar a etapa compartilhada em um só lugar e ela será refletida em todos os testes que a referência.

1. Clique no link do caso de teste na seção de **Resumo**.

    ![](images/085.png)

1. Clique duas vezes no caso para abri-lo no editor de caso de teste.

    ![](images/086.png)

1. Selecione as etapas 2-4 (use**Shift + clique**) e clique no botão **Criar passos compartilhadas**.

    ![](images/087.png)

1. Definir o nome dessas etapas compartilhadas para "**Add Disk and Pad Combo to cart**" e clique em **Criar**.

    ![](images/088.png)

1. Agora você pode ver as etapas anteriores substituídas pelos passos compartilhados. Clique duas vezes nas etapas compartilhadas para abrir.

    ![](images/089.png)

1. Se necessário, você pode revisitar essas etapas mais tarde para atualizá-las para novos requisitos.

    ![](images/090.png)

1. Pressione **Esc** para fechar o dialogo de **Passos compartilhadas**.

1. Clique **Salvar & fechar** para salvar o caso de teste.

    ![](images/091.png)
