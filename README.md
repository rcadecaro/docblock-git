# Guia para uso do GIT

[editar no GitHub](https://github.com/rcadecaro/docblock-git/edit/master/README.md) 

## Adicione a Chave publica no servidor do GIT

No github você pode copiar a chave publica gerada na sua máquina na seguinte [url do github](https://github.com/settings/keys)

## Clonar Repositórios

Para clonar um repositório este é o comando mais comum no github utilizando ssh:
```markdown
> git clone git@github.com:<username>/<nome-projeto>.git <pasta_local>
```
Por exemplo, este repositório poderia ser clonado com o seguinte comando:
```markdown
> git clone git@github.com:rcadecaro/docblock-git.git
```

**se você clonar o projeto não é preciso inicializar o git no diretorio clonado nem adicionar a referência ao github**

### Iniciar o controle git em um diretório

Para iniciar um repositório este é o comando:
```markdown
~/pasta-raiz-do-projeto> git init
```

### adicionar a referencia ao github a um diretorio existente

Para iniciar um repositório este é o comando:
```markdown
>git remote add github git@github.com:rcadecaro/docblock-git.git
```

O comando git remote add possui dois argumentos:

- O nome do repositorio remoto, por exemplo, **github**
- Uma URL, por exemplo, https://github.com/user/repo.git ou neste caso, por ser ssh: **git@github.com:rcadecaro/docblock-git.git**

## Para controlar as versões

Você deve marcar os arquivos que serão efetivados para alteração
```markdown
>git add <arquivo>

>git add *
```
Para confirmar estas mudanças use

```markdown
>git commit -m "comentários das alterações"
```

O arquivo possui histórico local, mas ainda não no repositório remoto. Isso pode ser feito com o seguinte comando

```markdown
>git push origin master
```
caso tenha clonado o repositorio do github o comando ser o seguinte:
```markdown
>git push github master
```
O comando git push possui dois argumentos:

- O nome do repositorio remoto, por exemplo, **github** ou **origin**
- O nome do branch ou ramificação  **master**
  
## Para fazer alterações em uma ramificação separada

Você pode criar uma ramificação com o seguinte comando
```markdown
>git checkout -b <nome-da-ramificacao>
```

E disponibilizá-la no servidor remoto com o seguinte comando
```markdown
>git push <remote_name> <nome-da-ramificacao>
```

## Para anexar as alterações desta ramificação no controle principal

Você deve voltar para o ramo principal com o seguinte comando
```markdown
>git checkout master
```
E anexar as alterações da ramificação <nome-da-ramificacao> a este ramo com o seguinte comando
```markdown
>git merge <nome-da-ramificacao>
```
Caso a ramificação <nome-da-ramificacao> não seja mais importante, apague-a com o seguinte comando
```markdown
>git branch -d <nome-da-ramificacao>
```
Caso deseje forçar a exclusão
```markdown
>git branch -D <nome-da-ramificacao>
```  
Para deletar uma ramificação(branch) no servidor remoto
```markdown
>git push <remote_name> --delete <nome-da-ramificacao>
```    
Ou
```markdown
>git push <remote_name> :<nome-da-ramificacao>
```      
 
