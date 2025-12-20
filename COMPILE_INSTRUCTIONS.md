# Инструкция по компиляции LaTeX в PDF

## Вариант 1: Онлайн (Overleaf) - Рекомендуется

1. Перейдите на https://www.overleaf.com/
2. Создайте аккаунт (если нет)
3. Создайте новый проект
4. Загрузите файл `Project_Report.tex`
5. Загрузите все изображения из папок:
   - `Lab1_sa_sd/image.png`
   - `Lab2_sa_sd/Lab2_sa_sd.png`
   - `Lab2_sa_sd/Lab2_sa_sd_returning.png`
   - `Lab3_sa_sd/Lab3_sa_sd.png`
   - `Lab4_sa_sd/C1-diagram.png`
   - `Lab4_sa_sd/C2-diagram.png`
   - `Lab4_sa_sd/C3-diagram.png`
   - `Lab4_sa_sd/C4-diagram.png`
   - `Lab4_sa_sd/Sequence Diagram.png`
6. Нажмите "Recompile" - PDF будет сгенерирован автоматически

## Вариант 2: Установка LaTeX локально (macOS)

### Установка через Homebrew:

```bash
# Установка BasicTeX (легковесная версия, ~100 МБ)
brew install --cask basictex

# Или полная версия MacTeX (4+ ГБ)
brew install --cask mactex
```

После установки BasicTeX, установите дополнительные пакеты:
```bash
sudo tlmgr update --self
sudo tlmgr install collection-latexextra
```

### Компиляция:

```bash
cd /Users/admin/systems_analysis_systems-design_archive
pdflatex Project_Report.tex
pdflatex Project_Report.tex  # Запустите дважды для корректного содержания
```

## Вариант 3: Docker (если установлен Docker)

```bash
docker run --rm -v "$(pwd)":/data -w /data texlive/texlive:latest pdflatex Project_Report.tex
docker run --rm -v "$(pwd)":/data -w /data texlive/texlive:latest pdflatex Project_Report.tex
```

## Примечания

- Если используете пути к изображениям, убедитесь, что все файлы находятся в правильных папках
- Для корректного содержания (tableofcontents) нужно запустить `pdflatex` дважды
- При ошибках с пакетами может потребоваться установка дополнительных пакетов через `tlmgr`

