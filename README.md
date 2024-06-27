# Codigo-Pilha-Portugol
Código simples de Pilha de Livros feito no Portugol Studio, permite adicionar um livro na pilha, remover o primeiro livro (no caso da pilha, o primeiro a ser removido é o último que foi colocado), limpar toda pilha, listar, conferir status e sair do sistema.

programa
{
inclua biblioteca Util
inclua biblioteca Texto --> T
caracter opcao
const inteiro total = 20
cadeia livro[total], busca, enter, resposta
inteiro ponteiro = 0, n, x

	funcao inicio()
	{
		limpa()
		escreva("=================== MENU ==================\n")
		escreva("1 - Adicionar um novo livro na pilha\n")
		escreva("2 - Remover o primeiro livro da pilha\n")
		escreva("3 - Limpar todos os livros da pilha\n")
		escreva("4 - Listar todos os livros da pilha\n")
		escreva("5 - Conferir status da pilha\n")
		escreva("6 - Sair do Sistema\n")
		escreva("===========================================\n")
		escreva("Escolha uma das opções: ")
		leia(opcao)
		limpa()

		escolha(opcao)
		{
			caso '1':
			{
				adicionar()
				pare
			}


			caso '2':
			{
				remover()
				pare
			}

			caso '3':
			{
				limpar()
				pare
			}

			caso '4':
			{
				listar()
				pare
			}

			caso '5':
			{
				situacao()
				pare
			}

			caso '6':
			{
				sair()
				pare
			}

			caso contrario:
			{
				escreva("Opção inválida, por favor escolha novamente\n")
				Util.aguarde(2000)
				inicio()
			}
		}
	}

	funcao adicionar()
	{
		se(ponteiro < 20)
		{
		escreva("========= ADICIONAR LIVRO NA PILHA =========\n")
		escreva("Qual livro você deseja adicionar na pilha?\n")
		leia(livro[ponteiro])
		livro[ponteiro] = T.caixa_alta(livro[ponteiro])
		limpa()
		
			escreva("Livro adicionado com sucesso\n")
			ponteiro++
			Util.aguarde(1000)
			inicio()
		}


		senao
		{
			escreva("Desculpe, não há mais espaço livre na pilha para um novo livro\n")
			retornar()
		}

	}

	
	funcao remover()
	{
		para(n=20; n<ponteiro -1; n++)
		{
			livro[n] = livro[n+1]
		}
		ponteiro--

		escreva("Primeiro livro retirado. Boa leitura!\n")
		retornar()

	}


	funcao limpar()
	{
		escreva("Deseja realmente limpar todos os livros da pilha? S/N \n")
		leia(resposta)
		resposta=T.caixa_alta(resposta)

		se(resposta=="S" ou resposta=="s")
		{
			limpa()
			escreva("Removendo todos os livros da pilha . . .\n")
			Util.aguarde(1000)
			escreva("Todos os livros foram removidos\n")
			ponteiro=0
			retornar()
		}

		senao
		{
			escreva("Nenhum livro foi removido da pilha\n")
			retornar()
		}
	}

	funcao listar()
	{
		
		limpa()
		se(ponteiro==0)
		{
			escreva("AVISO: Nenhum livro foi encontrado na pilha!\n")
			retornar()
		}
		senao 
		{
			para(x = ponteiro-1; x>=0; x-- )
			{
				escreva(x+1, "- Livro: " , livro[x], "\n")
			}
			retornar()
		}
	}

	funcao situacao()
	{

		se(ponteiro>=20)
		{
		escreva("===========================================\n")
		escreva("A pilha de livros já está cheia\n")
		escreva("===========================================\n")
		retornar()
		}

		se(ponteiro==0)
		{
		escreva("===========================================\n")
		escreva("Não há nenhum livro na pilha\n")
		escreva("===========================================\n")
		retornar()
		}

		senao
		{
		escreva("===========================================\n")
		escreva("Ainda há espaço para mais livros na pilha\n")
		escreva("===========================================\n")
		retornar()
		}
		
	}

	funcao retornar()
	{
		
		escreva("===========================================\n")
		escreva("Pressione a tecla [ENTER] para sair\n")
		escreva("===========================================\n")
		leia(enter)
		inicio()
		
	}

	funcao sair()
	{
		escreva("===========================================\n")
		escreva("O sistema está sendo finalizado . . .\n")
		escreva("===========================================\n")
		Util.aguarde(2000)
	}
}
/* $$$ Portugol Studio $$$ 
 * 
 * Esta seção do arquivo guarda informações do Portugol Studio.
 * Você pode apagá-la se estiver utilizando outro editor.
 * 
 * @POSICAO-CURSOR = 30; 
 * @PONTOS-DE-PARADA = ;
 * @SIMBOLOS-INSPECIONADOS = {livro, 8, 7, 5}-{ponteiro, 9, 8, 8};
 * @FILTRO-ARVORE-TIPOS-DE-DADO = inteiro, real, logico, cadeia, caracter, vazio;
 * @FILTRO-ARVORE-TIPOS-DE-SIMBOLO = variavel, vetor, matriz, funcao;
 */

