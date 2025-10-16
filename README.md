## POSSÍVEIS melhorias

### Utilizar mais recursos do dataset
- Coluna **timestamp** em **ratings.csv**: útil para ponderar avaliações recentes ou criar filtros temporais;
- Coluna **genres** em **movies.csv**: útil para content-based ou filtragem híbrida;
- **tags.csv** contém tags dadas pelos usuários (userId, movieId, tag, timestamp). Pode ser usado para enriquecer perfis de filmes, criar recomendações baseadas em tags, ou para filtragem híbrida;
- **links.csv** mapeia movieId para IDs externos (IMDb, TMDb). Útil para integrar dados externos, imagens de pôster, trailers, etc.

### Qualidade do modelo
- **Normalização das notas:** subtrair a média de cada usuário antes de calcular similaridade ajuda a reduzir viés de usuários mais “generosos” ou “severos”;
- **Filtragem baseada em similaridade ponderada:** em vez de apenas somar notas de filmes similares, multiplicar pelo grau de similaridade (já feito parcialmente) e normalizar pelo total de similaridades;
- **Considerar apenas vizinhos mais próximos:** para cada filme/usuário, considerar apenas os top K vizinhos mais similares, evitando ruído de itens pouco relevantes;

### Melhor UX/Interpretação
- **Exibir notas previstas + similaridade:** exibir no output uma ideia de por que aquele filme foi recomendado;
- **Recomendações filtradas:** evitar recomendar filmes que o usuário já avaliou.

### Abordagens híbridas
Combinar conteúdo + collaborative filtering: se temos gêneros, tags ou descrições de filmes (movies.csv tem gêneros), pode-se ponderar recomendações usando similaridade de conteúdo. Isso ajuda a mitigar problemas de cold-start (usuários ou filmes novos sem histórico).

### Interatividade e prototipagem
- Incluir input para escolher usuário ou filme e gerar recomendações na hora;
- Mostrar heatmaps de similaridade ou gráficos dos filmes recomendados por gênero;
- Exportar resultados: salvar top-N recomendações por usuário em CSV para análise posterior.