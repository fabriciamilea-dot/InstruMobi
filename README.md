# InstruMobi — primeira versão

Aplicativo web instalável (PWA) para fins acadêmicos, destinado a demonstrar aquisição de dados de movimento no Android, inclinação relativa, vibração estimada, alarmes e exportação CSV.

## Arquivos
- `index.html`: interface e lógica de aquisição/processamento.
- `manifest.webmanifest`: metadados de instalação PWA.
- `sw.js`: cache básico para funcionamento offline depois da primeira abertura.
- `icon.svg`: ícone vetorial.
- `RELATORIO_BASE.md`: estrutura inicial do relatório acadêmico.

## Como testar no Android
1. Publique os arquivos em um servidor HTTPS (por exemplo, GitHub Pages).
2. Abra a URL no Chrome do Android.
3. Toque em **Iniciar medições** e permita o acesso aos sensores, se solicitado.
4. Mantenha o aparelho parado e toque em **Calibrar referência** para definir a posição inicial.
5. Incline e mova suavemente o aparelho para observar as leituras.
6. Ajuste os limites dos alarmes e exporte os dados CSV.
7. Para instalar, use o menu do Chrome → **Adicionar à tela inicial** ou **Instalar app**, conforme a opção apresentada.

## Limitações técnicas importantes
- É necessário HTTPS (ou localhost) para suporte consistente a recursos do navegador.
- Disponibilidade e taxa de amostragem dependem do aparelho e do navegador.
- A inclinação é relativa à posição de calibração e é uma estimativa baseada nos ângulos beta/gamma.
- A vibração é uma estimativa filtrada da aceleração. Se o navegador disponibilizar `acceleration` sem gravidade, essa fonte é priorizada; caso contrário, a aceleração incluindo gravidade é filtrada. Não é uma medição certificada de vibração industrial.
- A aplicação depende de a tela permanecer ativa durante a coleta; navegadores podem suspender sensores em segundo plano.
- O histórico é mantido em memória durante a sessão. Exporte CSV antes de fechar ou recarregar a página.
- Alarmes usam vibração do próprio celular quando a API `navigator.vibrate` está disponível.
- Não utilizar para segurança funcional, avaliação certificada de máquinas ou decisões industriais críticas.

## Arquitetura
Sensores Android → APIs DeviceOrientation/DeviceMotion do navegador → processamento de inclinação e aceleração dinâmica → avaliação de limites → interface/gráfico → exportação CSV.

## Próximas melhorias
- Filtro e cálculo de RMS em janela temporal rigorosa.
- Persistência local das sessões.
- Testes de repetibilidade comparando diferentes orientações e aparelhos.
- Calibração com referência física conhecida.
- Relatório PDF e identificação da sessão.
