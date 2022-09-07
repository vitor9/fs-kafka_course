# 10 - Garantia de entrega de mensagens II

Outras formas de garantia de entregas que temos para o Kafka são…

- At most once: Melhor performance. Pode perder algumas mensagens
    
    ![68778C1D-9290-4FAB-8410-E4174DB8415B.jpeg](10%20-%20Garantia%20de%20entrega%20de%20mensagens%20II%20942538e218e243b081afb5dbbd0beeb5/68778C1D-9290-4FAB-8410-E4174DB8415B.jpeg)
    

- At least once: Performance moderada. Pode duplicar mensagens. Temos que garantir que o sistema vai excluir a duplicidade
- Exactly once: Pior performance. Exatamente uma vez. O Kafka fica se garantindo que o consumidor nunca vai receber duplicado, ou que vai perder uma msg.