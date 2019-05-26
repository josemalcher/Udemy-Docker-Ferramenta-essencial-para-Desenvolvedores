
# Docker: Ferramenta essencial para Desenvolvedores

https://www.udemy.com/curso-docker/learn/v4/overview

"No curso você aprenderá os principais conceitos do Docker com vários exercícios práticos, todos descritos detalhadamente na apostila que será disponibilizada no curso. Tudo que for ministrado no curso estará disponível na apostila, e ter esse suporte a mais, será um diferencial fantástico." 

## <a name="indice">Índice</a>

1. [Seção: 1 - Introdução (5)](#parte1)     
2. [Seção: 2 - Conceitos (6)](#parte2)     
3. [Seção: 3 - Instalação (4)](#parte3)     
4. [Seção: 4 - Uso Básico do Docker (14)](#parte4)     
5. [Seção: 5 - Deixando de Ser Apenas um Usuário (11)](#parte5)     
6. [Seção: 6 - Redes (4)](#parte6)     
7. [Seção: 7 - Coordenando Múltiplos Containers (2)](#parte7)     
8. [Seção: 8 - Projeto Cadastro Simples (3)](#parte8)     
9. [Seção: 9 - Projeto para Envio de E-mails com Workers (11)](#parte9)     
---


## <a name="parte1">Seção: 1 - Introdução (5)</a>

- [Mateiral do Curso/Instrutor](https://github.com/josemalcher/curso-docker)

- [PDF do curso](pdf/apostila-docker.pdf)

[Voltar ao Índice](#indice)

---


## <a name="parte2"> Seção: 2 - Conceitos (6)</a>

#### 1.1. O que é Docker?

É uma ferramenta que se apoia em recursos existentes no kernel, inicialmente Linux, para isolar a execução de processos. As ferramentas que o Docker traz são basicamente uma camada de administração de containers, baseado originalmente no LXC.

Alguns isolamentos possíveis:
- Limites de uso de memória
- Limites de uso de CPU
- Limites de uso de I/O
- Limites de uso de rede
- Isolamento da rede (que redes e portas são acessíveis)
- Isolamento do file system
- Permissões e Políticas
- Capacidades do kernel

Podemos concluir dizendo que estes recursos já existiam no kernel a um certo tempo, o que o Docker nos trouxe foi uma maneira simples e efetiva de utiliza-los.
- https://www.docker.com/what-docker

Containers Docker empacotam componentes de software em um sistema de arquivos completo, que contêm tudo necessário para a execução: código, runtime, ferramentas de sistema - qualquer coisa que possa ser instalada em um servidor.

Isto garante que o software sempre irá executar da mesma forma, independente do seu ambiente.

#### 1.2. Por que não uma VM?

O Docker tende a utilizar menos recursos que uma VM tradicional, um dos motivos é não precisar de uma pilha completa como vemos em Comparação VMs × Containers. O Docker utiliza o mesmo
kernel do host, e ainda pode compartilhar bibliotecas.

Mesmo utilizando o mesmo kernel é possível utilizar outra distribuição com versões diferentes das bibliotecas e aplicativos.

![](img/1-2-Por-que-nao-uma-VM.png)

Figura 1. Comparação VMs × Containers

Virtual Machine (máquina virtual), recurso extremamente usado atualmente para isolamento de serviços, replicação e melhor aproveitamento do poder de processamente de uma máquina física.

Devo trocar então minha VM por um container? Nem sempre, os containers Docker possuem algumas limitações em relação as VMs:
- Todas as imagens são linux, apesar do host poder ser qualquer SO que use ou emule um kernel linux, as imagens em si serão baseadas em linux.
- Não é possível usar um kernel diferente do host, o Docker Engine estará executando sob uma determinada versão (ou emulação) do kernel linux, e não é possível executar uma versão diferente, pois as imagens não possuem kernel.

#### 1.3. O que são containers?

Container é o nome dado para a segregação de processos no mesmo kernel, de forma que o processo seja isolado o máximo possível de todo o resto do ambiente.

Em termos práticos são File Systems, criados a partir de uma "imagem" e que podem possuir também algumas características próprias.

![](img/1-3-O-que-sao-containers.png)

- https://www.docker.com/what-container



#### 1.4. O que são imagens Docker?

Uma imagem Docker é a materialização de um modelo de um sistema de arquivos, modelo este produzido através de um processo chamado build.

Esta imagem é representada por um ou mais arquivos e pode ser armazenada em um repositório.

**Docker File Systems**

O Docker utiliza file systems especiais para otimizar o uso, transferência e armazenamento das imagens, containers e volumes.

O principal é o AUFS, que armazena os dados em camadas sobrepostas, e somente a camada mais recente é gravável.
- https://pt.wikipedia.org/wiki/Aufs
- https://docs.docker.com/engine/userguide/storagedriver/aufs-driver/


#### 1.5. Arquitetura

De maneira simplificada podemos dizer que o uso mais básico do Docker consiste em:
- Ter o serviço Docker Engine rodando
- Ter acesso a API Rest do Docker Engine, normalmente através do Docker Client
- Baixar uma imagem do Docker Registry, normalmente do registry público oficial: https://hub.docker.com
- Instanciar um container a partir da imagem baixada

![](img/1-5-Arquitetura.png)

Figura 2. Arquitetura do Docker


#### 1.6. Crescimento do Docker

A primeira versão do Docker é de 13 de março de 2013, tendo um pouco mais de 4 anos (na epóca que este curso foi escrito).

Nestes 4 anos ele tem se tornado cada vez mais popular e uma solução real para desenvolvedores (manter o seu ambiente mais simples e próximo à produção), administradores de sistema e ultimamente para uso enterprise, sendo avaliado pelos principais players do mercado uma alternativa mais econômica em relação as soluções atuais. Em sua maioria virtualização.

![](img/1-6-Crescimento-do-Docker.png)

[Voltar ao Índice](#indice)

---


## <a name="parte3"> Seção: 3 - Instalação (4)</a>



[Voltar ao Índice](#indice)

---


## <a name="parte4"> Seção: 4 - Uso Básico do Docker (14)</a>



[Voltar ao Índice](#indice)

---


## <a name="parte5"> Seção: 5 - Deixando de Ser Apenas um Usuário (11)</a>



[Voltar ao Índice](#indice)

---


## <a name="parte6"> Seção: 6 - Redes (4)</a>



[Voltar ao Índice](#indice)

---


## <a name="parte7"> Seção: 7 - Coordenando Múltiplos Containers (2)</a>



[Voltar ao Índice](#indice)

---


## <a name="parte8"> Seção: 8 - Projeto Cadastro Simples (3)</a>



[Voltar ao Índice](#indice)

---


## <a name="parte9"> Seção: 9 - Projeto para Envio de E-mails com Workers (11)</a>



[Voltar ao Índice](#indice)

---


