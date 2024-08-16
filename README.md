# Integração do Google Workspace com o Okta

- Para seguir com esse passo a passo, você já deve possuir uma conta Okta e uma conta Google.
- Você pode utilizar uma conta Trial do Okta. No entanto, ao adquirir as licenças, você deve alterar as configurações de SAML, visto que a URL altera o nome "trial" para outro nome.
https://support.okta.com/help/s/article/Renaming-Your-Okta-Subdomain?language=en_US
- Estamos contando nesse passo a passo uma configuração básica. Posteriormente você pode realizar outras configurações.

1.	No Okta Admin Dashboard, clique em **Applications / Applications**. Então selecione o botão **Browse App Catalog**.
![image](https://github.com/user-attachments/assets/3eff28e9-4d8e-4147-b4d1-0b9b1aa50a3f)

2.	Digite o nome do aplicativo no campo de busca. Clique em **Google Workspace**.
![image](https://github.com/user-attachments/assets/e4579e13-6abc-4435-820d-a0c0560eef1b)

3.	Clique em **Add Integration**.
![image](https://github.com/user-attachments/assets/8b0bf829-b3b7-488b-b625-e85ed795c718)

4.	Insira o domínio da empresa que será utilizada no Google Apps.
![image](https://github.com/user-attachments/assets/01ae4180-70ae-4eed-9db1-f7b381714ec6)

5.	Clique em **Next** para continuar.
![image](https://github.com/user-attachments/assets/5976f313-ef28-40f3-b932-a58c86f35e3c)

6.	Escolha a opção **SAML 2.0**.
![image](https://github.com/user-attachments/assets/77fbe6eb-c849-4f15-bf69-1491ec2eabf9)

7.	Role a página um pouco, e clique em **View Setup Instructions**. Será aberta uma nova aba com informações que serão utilizadas para a configuração no Google. Anote os dados e/ou mantenha essa nova página aberta.
![image](https://github.com/user-attachments/assets/92980c33-96b1-484b-b834-ab97a66e9b31)

8.	No **Google Admin Console**, clique em **Segurança / Autenticação / SSO com IdP de terceiros**.
![image](https://github.com/user-attachments/assets/29cb191b-96f9-4bbf-84aa-39868f4621cd)

9.	Agora teremos a opção de configurar um único SSO (Root Organization), ou vários perfis de SSO (Multi-IdP SSO Profile). Neste caso, usaremos a opção **Root Organization**. Mas cuidado. ao habilitar esse recurso, ele é aplicado por padrão a unidade organizacional raiz de toda a conta do Google. Para evitar isso, você pode desativar o **Perfil de SSO da organização** e escolher **nenhum** na unidade organizacional raiz.
![image](https://github.com/user-attachments/assets/0de04785-a11d-4788-807f-1623ba986a4c)

10.	Complete os dados da página, conforme os dados que foram fornecidos pelo Okta (Item 7). Para fazer o upload do certificado, você precisa ir à página aberta pelo OKta (Item 7), e clicar em **Verification Certificate**, para realizar o download do certificado.
![image](https://github.com/user-attachments/assets/2f002891-58ad-4f6a-830f-0c99aa0bd972)
![image](https://github.com/user-attachments/assets/620c8d25-69ce-4865-8ecc-b23ac005c8e3)
 
11.	Volte a console do **Okta**, e clique em **Done**, para concluir a adição da aplicação SAML.
![image](https://github.com/user-attachments/assets/129a3e25-5270-4295-aee1-56d914d52c5d)

12.	Selecione a aba **Provisioning**, e role até o final da página. Clique no botão **Configure API Integration**. Será habilitado o check box **Enable API integration**. Marque essa caixa. Clique no botão **Authenticate with Google Workspace**.
![image](https://github.com/user-attachments/assets/e8fe8110-46a2-48e2-b8b1-3ae23a73f94e)
![image](https://github.com/user-attachments/assets/ae0aeb78-ddc8-4d0b-aaba-a75401d0c540)
![image](https://github.com/user-attachments/assets/99c82919-333a-432f-a994-3d30b8a21e76)

13.	Entre com as informações de uma conta com privilégios de administrador na conta do Google Workspace para dar os privilégios necessários para o aplicativo Okta.
![image](https://github.com/user-attachments/assets/f6495532-51a0-40b6-af12-24522ca5689a)
![image](https://github.com/user-attachments/assets/de6eaed1-9a28-4daf-be12-6923d011f291)
![image](https://github.com/user-attachments/assets/b09ea6e4-6dac-4a37-a50e-d9cc84027e7d)

14.	Após as validações terem ocorrido com sucesso, clique em **Save**.
![image](https://github.com/user-attachments/assets/ad6facb3-4aab-41ea-9e84-6d8896e90c50)

15.	Se você deseja que o Okta possa criar, editar atributos de usuários e desativar usuários, na tela abaixo, clique em **Edit**, e marque as caixas de seleção. E então clique em **Save**. Esse passo é interessante para que não aconteça de você desativar um usuário no Okta, mas ele continue ativo no Google Workspace, por exemplo.
![image](https://github.com/user-attachments/assets/4b84f7b4-1b68-49ad-b6fe-1c5b23f1d412)

16.	Vá até a aba **Import**, e clique em **Import Now**, e aguarde o fim da importação dos usuários (note que você neste momento não está atribuindo serviços ao usuário ainda, está apenas importando para a console do Okta).
![image](https://github.com/user-attachments/assets/234ba2af-24c3-47b2-b0b0-bd46052d5676)
![image](https://github.com/user-attachments/assets/920b4950-753a-42e6-a7be-c5a2dea574d4)
![image](https://github.com/user-attachments/assets/2af7c504-a6f8-43bd-81bf-2f48787bb4ea)

17.	O Okta exibirá os usuários que serão adicionados. Marque as caixas de seleção com os usuários que devem ser importados e clique em **Confirm Assignments**. Não adicione uma conta Super Admin do Google para funcionar com o Okta. Manter assim é mais seguro para que você possa acessar sua conta do Google caso apresente algum problema na integração do Google com o Okta.
![image](https://github.com/user-attachments/assets/40dc43d8-84fd-4a1d-9b5e-b730d7189763)

18.	Se quiser habilitar o usuário assim que adicionado, marque a caixa de seleção **Auto-activate users after confirmation**.
![image](https://github.com/user-attachments/assets/b31b5748-b6ed-4b3a-b30c-591e770251e2)

19.	Assim que o usuário for ativado, ele receberá um e-mail para ativar a Okta Account. 
![image](https://github.com/user-attachments/assets/eecbd368-dcb4-4d36-acf2-039f73b4e535)
![image](https://github.com/user-attachments/assets/021a18d0-f0e7-4a3a-a3f3-18609476e64a)
![image](https://github.com/user-attachments/assets/d5daf07d-963b-428e-bf10-4a8a3825e391)

20.	Se você tiver habilitado a autenticação de duplo fator (habilitado por padrão), deve clicar em configurar. Caso contrário, clique em **Continuar**. Conclua o processo de ativação do usuário. O usuário deverá instalar o Okta Verify em seu smartphone para concluir o processo. É possível utilizar outros aplicativos de MFA se você habilitar, mas aqui estamos usando o padrão do Okta.
![image](https://github.com/user-attachments/assets/f5a9da7f-ec11-489d-9930-f42ec11384e7)

21.	De volta ao **Google Admin Console**, clique em **Diretório / Unidades Organizacionais**.
![image](https://github.com/user-attachments/assets/ff18efd1-dc87-4e10-a34e-debbd64b2a5c)

22.	Crie uma unidade organizacional chamada **Okta Enabled**. Você pode criar quantos você quiser, ou até mesmo utilizar o que você já possui. Neste caso, não esqueça de habilitar o perfil de SSO para cada uma das Unidades Organizacionais em que os usuários pertencentes a ela devem utilizar o Okta para autenticação. Você pode também habilitar para toda a organização (Unidade Organizacional raiz). Mas desse modo você pode fazer a migração por fases, e evitar possíveis problemas.
![image](https://github.com/user-attachments/assets/47b4a56b-f1ee-4d7a-9161-2bbf95506ff8)

23.	Clique em **Diretório / Usuários**. Em **Todas as organizações**, selecione **Usuários de unidades organizacionais selecionadas**. Selecione o(s) usuários(os), clique em **Mais opções e Alterar unidade organizacional**.
![image](https://github.com/user-attachments/assets/74db5c41-8686-4e7e-b739-7458ac7e499d)

24.	Selecione a unidade organizacional **Okta Enabled** e clique em **Continuar**. (Todos os usuários que estiverem nessa unidade organizacional, estarão habilitados a utilizar o Okta durante o login no Google Workspace. Os demais continuarão a acessar o Google Workspace sem serem transferidos para autenticar no Okta. Isso o auxiliará a realizar uma migração por fases de uma maneira mais tranquila.
![image](https://github.com/user-attachments/assets/a19550b2-ad46-415a-8583-07d1c17b2e01)
![image](https://github.com/user-attachments/assets/873c6f5a-11d0-4053-a95a-c9da3b755e7a)

25.	Vá em **Segurança / Autenticação / SSO com IdP de terceiros**.
![image](https://github.com/user-attachments/assets/c67a8123-d102-41ff-8fff-7a2ef713b817)

26.	No campo **Gerenciar atribuições do perfil de SSO**, clique em **Começar**.
![image](https://github.com/user-attachments/assets/75e73ffe-8c15-4682-be0b-bde1afd711f2)

27.	A esquerda, selecione a unidade organizacional criada, chamada **Okta Enabled**. No momento vamos habilitar o Okta para os usuários pertencentes a esta Unidade Organizacional, mas você pode adicionar em mais de uma.
![image](https://github.com/user-attachments/assets/88eef133-544d-4779-851e-d713df3e63c6)

28.	No campo a direita, já com o  escopo selecionado, selecione **Perfil de SSO de terceiros da organização**, e então clique em **Salvar**. Dica: Você pode desativar perfil SSO na raiz das unidades organizacionais, e ir habilitando somente nas unidades organizacionais que você deseja que os usuários tenham o Okta habilitado. Isso evita problemas ao ativar tudo de uma vez.
![image](https://github.com/user-attachments/assets/6f17f547-9fbf-444d-af1c-f3f2308f3acf)
![image](https://github.com/user-attachments/assets/3231dc7e-824c-4dde-8af1-8e153753bb8d)

30.	Agora, basta abrir algum serviço do Google, como o Gmail por exemplo, e você notará que quando o usuário inserir o seu usuário (que estiver com o Okta habilitado, conforme passos 25 e 26), ele será encaminhado para uma tela de autenticação do Okta. Uma vez que ele estiver validado, será transferido para o Google normalmente.
![image](https://github.com/user-attachments/assets/3b428880-f3f7-4b6d-93fa-62169926c9c6)
![image](https://github.com/user-attachments/assets/2b1d6f65-eb4b-468c-bc66-9a64880e2f77)
