## Top-K Neighbors (Item-based)
- Para cada filme, o código seleciona apenas os K filmes mais similares (vizinhos) com base na similaridade coseno.
- Similaridades negativas são ignoradas e o próprio filme é removido.
- Esse Top-K é usado para acalcular notas previstas para usuários:
    - Somando as notas que o usuário deu aos vizinhos, ponderadas pela similaridade.
    - Normalizando pela soma das similaridades (evita inflar scores por excesso de vizinhos).

Resultado: recomendações mais precisas e robustas, evitando que vizinhos pouco relevantes “diluam” a previsão.
Ajuda a controlar ruído e melhora a escalabilidade, porque não precisa considerar todos os filmes da base.