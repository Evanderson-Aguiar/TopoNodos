# TopoNodos – QGIS Plugin

**TopoNodos** é um plugin para o QGIS que identifica automaticamente pontos de inflexão altimétrica ao longo de redes de distribuição baseadas em um Modelo Digital de Superfície (MDS). Ele permite a extração de nós com variações significativas de declividade e a segmentação das tubulações nesses pontos, oferecendo suporte à análise de traçado e ao planejamento hidráulico de redes.

---

## 🛠️ Funcionalidades

- Identificação automática de **pontos de inflexão** ao longo de tubulações vetoriais.
- **Amostragem de elevação** a partir de um MDS (modelo raster).
- Quebra da geometria original da linha **preservando os vértices** entre os pontos de inflexão.
- Geração de:
  - Camada de **pontos** com elevação e ID da linha.


---

## 🔍 Aplicações

- Estudos altimétricos e análise de traçado de redes de água/esgoto.
- Identificação de trechos críticos com inversão de declividade.
- Modelagem hidráulica em softwares como EPANET e WNTR.
- Suporte ao geoprocessamento em projetos de saneamento básico e infraestrutura.

---

## 🚀 Como usar

### 1. Instale o plugin

Você pode instalar diretamente pelo QGIS (após publicação) ou carregar localmente:

- Vá em **Complementos > Gerenciar e Instalar Complementos > Instalar a partir de ZIP**
- Selecione o arquivo `TopoNodos.zip`

### 2. Execute o algoritmo

- Acesse **Caixa de Ferramentas > TopoNodos**
- Execute o algoritmo informando:
  - **MDS**: raster de elevação (com unidades em metros ou graus)
  - **Tubulações**: camada vetorial de linhas (rede de distribuição)
  - **Fator de suavização**: mínima variação altimétrica para ser considerada inflexão (em metros)
  - **Passo de interpolação**: distância entre os pontos amostrados na linha (em metros)

### 3. Resultados

- Camada de **linhas segmentadas** nos pontos de inflexão.
- Camada de **pontos** com elevação amostrada.

---

## 📦 Estrutura dos arquivos de saída

### Linhas segmentadas
| Campo        | Descrição                     |
|--------------|-------------------------------|
| [atributos da linha original] | Mantidos do input |

### Pontos de inflexão
| Campo      | Descrição                              |
|------------|------------------------------------------|
| `elev`     | Elevação amostrada no ponto (metros)     |
| `id_linha` | ID da feição de origem da tubulação      |

---

## 📐 Requisitos

- QGIS ≥ 3.10
- Um raster de elevação coerente com a área de estudo
- Tubulações como geometrias do tipo `LineString`

---

## 🧑‍💻 Autor

Evanderson H. Aguiar  
📧 evanderson.eng@gmail.com  
🔗 [github.com/Evanderson-Aguiar/TopoNodos](https://github.com/Evanderson-Aguiar/TopoNodos)

---

## 📄 Licença

Este plugin está licenciado sob a [GPL v2 ou superior](https://www.gnu.org/licenses/old-licenses/gpl-2.0.html).
