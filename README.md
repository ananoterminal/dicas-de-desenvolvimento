# Dicas de Desenvolvimento
### Este repositório é colaborativo e tem como objetivo reunir dicas legais de desenvolvimento.

---
**Dicas:**

1. Se você não vai usar o dado para cálculos prefira armazená-lo como string.

   1. Nunca valide o campo de CPF como inteiro, use o tipo string. Por exemplo: Se o CPF é `050.***.***.***-**` irá ficar `50*.***.***-*`.
   
2. Armazene só o que é necessário no dado. Não armazene caracteres de formatação. (ex.
   `12345678901` e não `123.456.789-01`.
3. Evite usar dados de negócio (ex. CPF, RG, placa de carro) na criação da sua modelagem.
   A estrutura, formato e função destes dados pode mudar com o tempo e quebrar a sua modelagem.
   
   1. Não use CPF como chave primária de uma tabela. Usar um índice do tipo UNIQUE melhor.
   2. Não confie muito no formato do dado para criar regras. Lembrem-se que as placas de carro
      brasileiras tinham só 2 letras, depois 3 letras e agora tem uma mistura de letras e
      números. Os CEPs brasileiros tinham 5 dígitos e agora tem 8.
      
4. Tente armazenar as datas em um timezone neutro (ex. UTC) e fazer as conversões para o timezone
   adequado apenas para entrada e saída dessa informação.

   1. Em alguns casos raros pode ser necessário saber o horário em que a ação ocorreu no local (ex.
      o vendedor postou a encomenda no horário comercial de Manaus onde ele mora?). Nesses casos
      grave as duas informações separadamente (ex. uma coluna com a data/hora UTC e outra com a
      data/hora local). Isso simplifica fazer operações com essas datas sem ter que ficar
      consultando alterações de timezone (ex. no ano em questão teve horário de verão nessa data?
      nesse país/estado?

5. Tenha curiosidade em entender como funciona a tecnologia que você usa.
    1. Não fique na zona de conforto de linguagens e frameworks. Procure entender como funciona
       "por debaixo dos panos" para assim você ter mais facilidade ao resolver um problema que possa ocorrer.
       Pesquise sobre conceitos de computação como Estruturas de Dados e Programação Orientada a Objetos, assim há chances
       de otimizar cada vez mais seu código.
