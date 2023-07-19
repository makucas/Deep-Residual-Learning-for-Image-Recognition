# Learning for Image Recognition

> Projeto desenvolvido durante a disciplina de Redes Neurais Profundas ministrada pelo professor Lucas Araújo Pereira na Universidade Federal de Goiás. Implementação em Python usando o Pytorch.

## Índice

- [Visão Geral](#visão-geral)
- [Implementação](#implementação)
- [Resultados](#resultados)
- [Referências](#referências)
- [Licença](#licença)

## Visão Geral

* A premissa do autor é de que conforme se aumenta a profundidade de uma rede plana, a taxa de erro tende a aumentar dada a degradação dos gradientes, o que é um problema, uma vez que redes mais profundas seriam capazes de extrair mais features.
* Dado essa problemática, ele introduz sua solução, as Redes Residuais, redes que permitem contornar o problema da degradação através de conexões especiais, e como é possível ver na imagem abaixo, as redes propostas(direita) apresentam comportamento inverso as redes planas(esquerda). 

![image](https://github.com/makucas/Deep-Residual-Learning-for-Image-Recognition/assets/46076494/cb81d308-5193-4065-9cd0-ad76d6fc3431)

## Implementação

* Como proposto pelo professor, a implementação do projeto foi realizada seguindo ao máximo as informações extraídas do paper.
* A entrada da rede são imagens de 32x32, a primeira camada é uma convolução 3x3, seguida de 6n camadas com convoluções 3x3 e finalizando com um global avarage pooling, uma 10-way fully-connected e uma softmax.
  
![image](https://github.com/makucas/Deep-Residual-Learning-for-Image-Recognition/assets/46076494/7ca803e6-f891-4a94-be08-37fcea47af1c)

* Como hiperparâmetros são utilizado de um weight decay de 0.0001, momentum em 0.9, batch size mínimo de 128, learning rate de 0.1, dividida por 10 em 32k e depois em 48k iterações, e terminando em 64k iterações.
*  Pesos e um batch normalization são ajustados seguindo referências de outros trabalhos acadêmicos. 
## Resultados

* Após executar o treinamento e teste para as redes de 20 e 32 camadas, os resultados obtidos foram os mesmos evidênciados no paper, a Resnet(esquerda) apresentou uma taxa de erro menor durante o processo de treinamento para camadas mais profundas, o que é positivo, permitindo-se utilizar mais layers em uma rede neural para extrair mais features e contornando o problema da degradação do gradiente.
* É válido ressaltar que o experimento executou o treinamento de todas as redes de uma única vez, mantendo os mesmos valores aleatórios para todas, processo que durou cerca de 6 horas no ambiente do Google Colab.
  
![image](https://github.com/makucas/Deep-Residual-Learning-for-Image-Recognition/assets/46076494/743a956e-f862-49ac-b35b-50f53a68b403)

## Referências
* Artigo utilizado como referência: https://arxiv.org/pdf/1512.03385.pdf

## Licença
[MIT](https://choosealicense.com/licenses/mit/)

