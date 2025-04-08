from PyPDF2 import PdfMerger
import os

# Define o caminho da pasta onde estão localizados os arquivos PDF
caminho = r'C:\Users\uni34517\Downloads\Plano de ensino'

# Cria uma instância do PdfMerger
merger = PdfMerger()

# Define o caminho do arquivo que deve ser a primeira página
arquivo_inicial = os.path.join(caminho, 'plano de ensino completo.pdf')

# Verifica se o arquivo inicial existe e o adiciona primeiro
if os.path.exists(arquivo_inicial):
    merger.append(arquivo_inicial)

# Lista todos os arquivos PDF da pasta, exceto o que já foi adicionado
pdfs = [
    os.path.join(caminho, f)
    for f in os.listdir(caminho)
    if f.endswith('.pdf') and f.lower() != 'plano de ensino completo.pdf'
]

# Ordena os arquivos restantes por data de modificação (mais antigos primeiro)
for arquivo in sorted(pdfs, key=os.path.getmtime):
    merger.append(arquivo)

# Salva o resultado final no arquivo "Meu_plano_de_ensino.pdf"
merger.write('Meu_plano_de_ensino.pdf')

# Fecha a instância do merger para liberar recursos
merger.close()
