# Yasnippet Snippets Collection

This repository contains my personal collection of [Yasnippet](https://github.com/joaotavora/yasnippet) snippets, organized by major mode.
It is meant to be a reusable snippet library that I can keep under version control and sync across machines.
Many have been inspired by [Karthinks](https://github.com/karthink/yasnippets) and [Gilles Castel (RIP)](https://castel.dev/post/lecture-notes-1/).

---

## Structure

The file [`treefile`](treefile) shows the directory layout:

```text
.
├── latex-mode
│   ├── curl-snippet
│   ├── dag
│   ├── feynman-slashed
│   ├── red-comment
│   └── times
├── LICENSE
├── org-mode
│   ├── math-snippets
│   │   ├── acute
│   │   ├── approx
│   │   ├── bar
│   │   ├── bra
│   │   ├── breve
│   │   ├── cdot
│   │   ├── check
│   │   ├── conj
│   │   ├── cube
│   │   ├── dag
│   │   ├── ddot
│   │   ├── definite integral
│   │   ├── definite sum
│   │   ├── derivative operator
│   │   ├── dot
│   │   ├── dots
│   │   ├── frac
│   │   ├── geq
│   │   ├── gg
│   │   ├── grave
│   │   ├── hat
│   │   ├── implies
│   │   ├── indefinite integral
│   │   ├── indefinite sum
│   │   ├── infinity
│   │   ├── inline-math-expression
│   │   ├── inner-product
│   │   ├── ket
│   │   ├── leq
│   │   ├── ll
│   │   ├── mathring
│   │   ├── mathrm-d
│   │   ├── melem
│   │   ├── neq
│   │   ├── odot
│   │   ├── otimes
│   │   ├── outer-product
│   │   ├── sim
│   │   ├── square
│   │   ├── tilde
│   │   ├── times
│   │   ├── to
│   │   ├── to-the-power
│   │   └── vec
│   ├── name
│   ├── org-bib
│   ├── org-bib-old
│   ├── quotation-mark
│   ├── source_blocks
│   │   ├── elisp-src
│   │   ├── julia-src
│   │   └── jupyter-src
│   ├── template-structure
│   ├── todays-date
│   └── transclusion-add
├── python-mode
│   ├── pandas
    └── scipy
```

The top-level layout is:

- `latex-mode/` – Snippets for LaTeX buffers  
  - Examples: `feynman-slashed`, `curl-snippet`, `dag`, `times`, `red-comment`
- `org-mode/` – Snippets for Org buffers  
  - `math-snippets/` – Inline and display math helpers (integrals, sums, products, bras/kets, vectors, etc.)  
  - `source_blocks/` – Templates for source blocks (Elisp, Julia, Jupyter, …)  
  - Other helpers: bibliography (`org-bib`), structure templates, dates, transclusion, and more
- `python-mode/` – Snippets for Python buffers  
  - Focused on scientific computing, e.g. `pandas`, `scipy`
- `treefile` – A snapshot of the directory tree (for quick reference)

---

## Installation

Clone this repository somewhere on your system, for example:

```bash
git clone https://github.com/<user>/<repo>.git ~/repos/snippets
```

Then, in your Emacs configuration:

```elisp
(require 'yasnippet)

(setq yas-snippet-dirs
      (append yas-snippet-dirs
              '("~/repos/snippets")))  ;; adjust path if needed

(yas-global-mode 1)
```

You can also add it as the only snippet directory:

```elisp
(setq yas-snippet-dirs '("~/repos/snippets"))
(yas-global-mode 1)
```

After reloading your configuration or restarting Emacs, the snippets should be available in the corresponding major modes.

---

## Usage

1. Open a buffer in a supported mode (e.g., `org-mode`, `latex-mode`, `python-mode`).
2. Type the snippet key (defined in each snippet file).
3. Press `TAB` (or whatever `yas-expand` is bound to) to expand.

To inspect keys and contents:

- `M-x yas-describe-tables` – List active snippets
- `M-x yas-visit-snippet-file` – Jump to the snippet definition

Because many snippets are math-related (especially in `org-mode/math-snippets` and `latex-mode`), they are particularly useful in scientific or technical writing workflows.

---

## Customization

This is a personal collection, but you are free to:

- Fork it and adapt the snippets to your own workflow.
- Add new language- or domain-specific directories (e.g. `julia-mode`, `sh-mode`, etc.).
- Modify or extend existing snippets (e.g. add conditions, interactive fields, or mirrors).

If you build on this repository, consider:

- Keeping one directory per major mode.
- Grouping related snippets into subdirectories (as with `org-mode/math-snippets`).
- Using descriptive names and clear keys.

---

## License

See [LICENSE](LICENSE) for licensing information.
```
