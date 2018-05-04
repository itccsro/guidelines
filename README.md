[![Slack](https://img.shields.io/badge/slack-%23guidelines-green.svg)](https://civictechro.slack.com/messages/CAFLVGYJ0/) 
[![GitHub license](https://img.shields.io/github/license/civictechro/guidelines.svg)](https://github.com/civictechro/guidelines/blob/master/LICENSE) 

[![GitHub issues by-label](https://img.shields.io/github/issues-raw/civictechro/guidelines/help%20wanted.svg)](https://github.com/civictechro/guidelines/issues) [![GitHub issues by-label](https://img.shields.io/github/issues-raw/civictechro/guidelines/good%20first%20task.svg)](https://github.com/civictechro/guidelines/issues) 

# Open Source Guidelines 

*https://civictechro.github.io/guidelines/*

CivicTech România își dorește să folosească potențialul tehnologiei Open Source și talentul specialiștilor români pentru a dezvolta noi servicii digitale de utilitate publică. 

Tocmai de aceea am creat și acest ghid, pentru a stabili împreună cum putem colabora la dezvoltarea acestor proiecte și pentru a strânge îm jurul nostru o comunitate de oameni cu aceeași viziune ca și noi. În redactarea acestor guidelines ne-am folosit de experiența dobândită în mediul privat și de bunele practici promovate acolo, dar și de experiența de până acum în CivicTech România și GovITHub. 

***
*Aceste guidelines sunt în continuă dezvoltare, folosind ca sursă de inspirație [The US Digital Services Playbook](https://playbook.cio.gov/), [GitHub Open Source Guides](https://opensource.guide/) dar și [setul de guidelines dezvoltat inițial](https://github.com/gov-ithub/guidelines) în cadrul GovITHub. Așteptăm propunerile voastre pe GitHub!*

## Detalii tehnice

Conținutul este compilat din fișiere [Markdown](https://help.github.com/articles/github-flavored-markdown "Link to More Information About Markdown"), folosind [Jekyll](https://github.com/jekyll/jekyll "Link to More Information about Jekyll").

### Cum rulez site-ul local?

Dacă vrei să rulezi site-ul local, va trebui să instalezi [Jekyll](https://github.com/jekyll/jekyll "Link to More Information about Jekyll") și dependințele sale.

1. Dacă nu ai deja Ruby și Bundler instalate, urmărește [cei doi pași pentru instalare](https://help.github.com/articles/using-jekyll-with-pages#installing-jekyll "Installation instructions for Jekyll").
2. Apoi, ai nevoie de [un fork al acestui repository](https://help.github.com/articles/fork-a-repo/ "Instructions for Forking Your Repository") pe care îl poți clona local.
3. Din root-ul proiectului, pe calculatorul tău, poți rula `bundle install` în terminal.

Pentru a rula site-ul local, rulează `jekyll serve --watch` din terminal, apoi deschide `http://localhost:4000/` în browser.

### Cum editez stylesheets?

Proiectul folosește [Sass](http://sass-lang.com/ "Link to Learn More About Sass") pentru management de CSS. Codul îl poți găsi în [`styles.scss` file](assets/_sass/styles.scss). Folosim [suportul SASS nativ pentru Jekyll](https://jekyllrb.com/docs/assets/) pentru a genera fișierele CSS, când rulezi site-ul local.

## Cum pot propune o schimbare de conținut?

Dacă vrei să propui o schimbare, trimite un [pull request](https://help.github.com/articles/creating-a-pull-request "More Information on Submitting Pull Requests"), cu o schimbare într-unul dintre fișierele Markdown. Fiecare guideline se poate găsi în [folderul `_plays`](https://github.com/civictechro/guidelines/tree/master/_plays). Introducerea se află în [folderul `_include`](https://github.com/civictechro/guidelines/tree/master/_include).

Fișierele se pot edita și direct în browser, fără a fi necesară instalarea de software adițional.

## Reguli generale

- Proiectul trebuie sa conțină un fișier README.md în care să apară informații relevante despre proiect.
- Cerințele și specificațiile trebuie să fie prezente în proiect. Dacă nu sunt, deschide un issue pe Github.
- Codul trebuie scris în engleză (e.g.: numele variabilelor).
- Componentele care interacționează cu utilizatorul trebuie să suporte [localizarea](https://en.wikipedia.org/wiki/Internationalization_and_localization) în diferite limbi.
 - Conținutul în limba română trebuie să folosească diacritice.
- Toate proiectele trebuie să aiba o copie a [licenței](LICENSE) folosite.
- Menționează canalul de Slack al proiectului în README.
- Prezența și rularea testelor nu este opțională.
- Documentația trebuie scrisă în timpul dezvoltării, nu după.

## Alte informații
- [Întrebări frecvente](/old_guides/FAQ.md)
- [Code Review](/old_guides/CODE_REVIEW.md)
- [Ghid de colaborare](/old_guides/CONTRIBUTING.md)
- [Ghid mesaje commit (en)](/old_guides/COMMIT.md)

CivicTech România este construit cu ajutorul voluntarilor.

----------

**Made with :heart: & :coffee: by [CivicTech România](https://civictech.ro/)**
