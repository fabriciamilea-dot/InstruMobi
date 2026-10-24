# Relatório-base — InstruMobi

## 1. Identificação
**Título:** InstruMobi — Sistema de monitoramento de inclinação e vibração por smartphone  
**Disciplina:** Laboratório de Instrumentação e Controle  
**Integrantes:** [preencher]  
**Professor(a):** [preencher]  
**Instituição:** [preencher]  
**Data:** [preencher]

## 2. Objetivo
Desenvolver um aplicativo didático para Android capaz de adquirir dados de movimento dos sensores internos do smartphone, estimar a inclinação relativa e a vibração, exibir gráficos, emitir alarmes por limites configuráveis e exportar as medições para análise.

## 3. Princípio de funcionamento
O aplicativo utiliza as APIs de movimento do navegador Android para receber eventos de orientação e aceleração. A orientação é comparada com uma referência estabelecida pelo usuário durante a calibração. A vibração é estimada pela componente dinâmica da aceleração após a atenuação de componentes lentas. O sistema compara as grandezas calculadas com limites definidos pelo usuário e sinaliza condições acima desses limites.

## 4. Arquitetura
Smartphone Android (sensores) → APIs DeviceOrientation/DeviceMotion → processamento digital → lógica de alarmes → interface gráfica e histórico → exportação CSV.

## 5. Variáveis e unidades
- Inclinação relativa: graus (°).
- Vibração estimada: aceleração RMS aproximada em metros por segundo ao quadrado (m/s²).
- Tempo de aquisição: marca temporal fornecida pelo sistema.

## 6. Materiais e ferramentas
- Smartphone Android com acelerômetro e suporte a eventos de movimento.
- Navegador compatível (preferencialmente Chrome).
- Aplicação InstruMobi (HTML, CSS e JavaScript).
- Servidor HTTPS para hospedagem da versão PWA.
- Objeto ou superfície estável para os testes de referência.

## 7. Procedimento experimental sugerido
1. Abrir o aplicativo em HTTPS e iniciar as medições.
2. Colocar o celular em uma superfície estável.
3. Calibrar a posição de referência.
4. Repetir três vezes uma sequência de inclinações conhecidas, por exemplo 0°, 10°, 20° e 30°, usando um transferidor como referência.
5. Aplicar movimentos suaves e repetíveis para comparar a resposta de vibração estimada.
6. Ajustar os limites de alarme e observar as sinalizações.
7. Exportar o CSV e comparar os resultados.

## 8. Resultados
Preencher após os testes reais. Incluir tabelas de valores de referência e medidos, gráficos, desvios observados e ocorrências de alarmes. Não inventar valores antes da execução experimental.

## 9. Limitações
O smartphone não é um instrumento de vibração calibrado. As APIs, filtros, e taxas de amostragem variam conforme o modelo e o navegador. A estimativa deve ser tratada como demonstrativa, e não como medição industrial certificada.

## 10. Conclusão
Preencher após a validação experimental, discutindo funcionamento, repetibilidade, limitações, custo e melhorias futuras.
