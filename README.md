📌 Revisão: DTO, Versionamento e Git
🚀 DTO (Data Transfer Object)
O DTO é um objeto usado para transferir dados entre o backend e o frontend sem expor diretamente a estrutura do banco de dados. Ele ajuda a reduzir o acoplamento e a melhorar a segurança.
📌 Exemplo:
 Se temos uma entidade no banco de dados chamada SuperHero, mas queremos enviar apenas alguns dados para o front, usamos um DTO:
csharp
Copiar código
public class SuperHeroDto
{
    public string Nome { get; set; }
    public string Poder { get; set; }
}

Agora, ao buscar os dados no backend, retornamos apenas os campos necessários:
csharp
Copiar código
public List<SuperHeroDto> ListarSuperHerois()
{
    return _superHeroService.BuscarTodos()
        .Select(h => new SuperHeroDto
        {
            Nome = h.Nome,
            Poder = h.Poder
        }).ToList();
}

Isso melhora a performance e evita expor informações desnecessárias.


📌 Comandos Frequentes do Git (Versionamento de Código)
O Git é uma ferramenta de controle de versão distribuída que ajuda a gerenciar e rastrear mudanças no código. Abaixo estão os comandos mais usados para o dia a dia de desenvolvimento.

📂 Configuração Inicial do Git
Antes de começar a usar o Git, configure seu nome e e-mail:
bash
Copiar código
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@example.com"

Para verificar a configuração:
bash
Copiar código
git config --list


🆕 Iniciar um Repositório
bash
Copiar código
git init

➡ Cria um repositório Git na pasta atual.
bash
Copiar código
git clone <url-do-repositorio>

➡ Clona um repositório remoto para sua máquina.

🔄 Trabalhando com Branches
bash
Copiar código
git branch

➡ Lista todas as branches no repositório.
bash
Copiar código
git branch <nome-da-branch>

➡ Cria uma nova branch.
bash
Copiar código
git checkout <nome-da-branch>

➡ Alterna para outra branch.
bash
Copiar código
git checkout -b <nova-branch> <branch-base>

➡ Cria uma nova branch baseada em outra branch existente.
bash
Copiar código
git merge <branch>

➡ Mescla a branch especificada com a atual.
bash
Copiar código
git branch -d <nome-da-branch>

➡ Exclui uma branch local.
bash
Copiar código
git push origin --delete <nome-da-branch>

➡ Exclui uma branch remota.

📥 Baixando Atualizações do Repositório
bash
Copiar código
git pull origin <nome-da-branch>

➡ Atualiza seu repositório local com as mudanças do repositório remoto.
bash
Copiar código
git fetch

➡ Busca as mudanças do repositório remoto, mas não as aplica automaticamente.

📤 Enviando Alterações para o Repositório Remoto
bash
Copiar código
git add .

➡ Adiciona todas as mudanças ao stage (preparação para commit).
bash
Copiar código
git add <nome-do-arquivo>

➡ Adiciona apenas um arquivo específico ao stage.
bash
Copiar código
git commit -m "mensagem do commit"

➡ Salva as mudanças localmente com uma mensagem explicativa.
bash
Copiar código
git push origin <nome-da-branch>

➡ Envia as mudanças para o repositório remoto.
bash
Copiar código
git push --force

➡ Força o envio das mudanças, sobrescrevendo o histórico remoto (use com cautela!).

🔄 Desfazendo Alterações
bash
Copiar código
git reset --soft HEAD~1

➡ Remove o último commit, mantendo as alterações no stage.
bash
Copiar código
git reset --hard HEAD~1

➡ Remove o último commit e descarta as alterações.
bash
Copiar código
git checkout -- <nome-do-arquivo>

➡ Restaura um arquivo modificado para a última versão commitada.
bash
Copiar código
git revert <commit-hash>

➡ Cria um novo commit que reverte as mudanças do commit especificado.

🔒 Armazenando Mudanças Temporariamente
bash
Copiar código
git stash

➡ Salva temporariamente alterações não commitadas.
bash
Copiar código
git stash pop

➡ Restaura as mudanças salvas e remove do stash.
bash
Copiar código
git stash list

➡ Lista todas as alterações salvas no stash.
bash
Copiar código
git stash drop

➡ Remove o stash mais recente.

📜 Visualizando o Histórico de Commits
bash
Copiar código
git log

➡ Exibe o histórico completo de commits.
bash
Copiar código
git log --oneline

➡ Exibe um histórico resumido dos commits.
bash
Copiar código
git log --graph --all --decorate --oneline

➡ Exibe um histórico gráfico das branches.
bash
Copiar código
git diff

➡ Mostra as diferenças entre o código atual e a última versão commitada.
bash
Copiar código
git status

➡ Exibe o status dos arquivos (modificados, adicionados, não rastreados, etc.).

🔥 Dicas Finais
Faça commits pequenos e frequentes para manter um histórico organizado.
Sempre escreva mensagens de commit descritivas, como:
 bash
Copiar código
git commit -m "Corrigido bug no formulário de login"


Antes de iniciar uma nova tarefa, crie uma branch separada, ex:
 bash
Copiar código
git checkout -b nova-feature


Sempre sincronize seu repositório antes de começar a trabalhar:
 bash
Copiar código
git pull origin main




