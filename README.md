# rosbot3_description

Este pacote fornece a descrição completa do ROSbot 3 utilizada na disciplina de robótica, permitindo carregar a geometria do robô.

## Conteúdo
- `urdf/base.xacro`: define a estrutura base do robô (corpo, eixos, rodas e propriedades geométricas compartilhadas).
- `urdf/rosbot3.xacro`: compõe a descrição final adicionando sensores (LiDAR e câmera), suportes e junções, usando as macros definidas em `base.xacro` e em `ros_commons`.
- `launch/display.launch`: lança o `robot_state_publisher` e carrega o modelo no RViz para visualização rápida.

## Adições relevantes
- Modelagem do suporte e da câmera frontal baseada nas dimensões do OAK-D Lite, incluindo offsets para posicionamento realista.
- Inclusão do sensor LiDAR com parâmetros de altura e deslocamento alinhados à documentação do ROSbot.

## Como utilizar
1. Inclua `rosbot3_description` como dependência nos seus pacotes que necessitam da descrição do robô.
2. Inicie a visualização com:
   ```bash
   ros2 launch rosbot3_description display.launch
   ```
3. Combine com `ros_commons` para adicionar plugins de simulação (como o `skid_steer_controller`) quando for executar no Gazebo.
