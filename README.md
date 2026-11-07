<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/brand/svg/floorcuttree-logo-on-dark.svg">
    <img src="docs/brand/svg/floorcuttree-logo-on-light.svg" alt="FloorCutTree" width="260">
  </picture>
</p>

<h1 align="center">Cut a floor plan. Find the smallest rectangle.</h1>

<p align="center">
  Archived university assignment in Java, 2019.<br>
  <b>A binary tree of horizontal and vertical cuts, compacted to its minimum size.</b>
</p>

<p align="center">
  <img alt="Status: archived" src="https://img.shields.io/badge/status-archived-A9762B?style=flat-square">
  <a href="LICENSE"><img alt="License: GPL-3.0" src="https://img.shields.io/badge/license-GPL--3.0-3b82f6?style=flat-square"></a>
  <img alt="Java" src="https://img.shields.io/badge/Java-JDK-ED8B00?style=flat-square&logo=openjdk&logoColor=white">
  <img alt="Eight directives" src="https://img.shields.io/badge/directives-8-1E2A38?style=flat-square">
  <a href="https://github.com/mertkayacs/FloorCutTree"><img alt="GitHub stars" src="https://img.shields.io/github/stars/mertkayacs/FloorCutTree?style=flat-square&logo=github&color=C4A772"></a>
</p>

<p align="center">
  <a href="#quick-start"><img alt="Run it" src="https://img.shields.io/badge/Run%20it-A9762B?style=for-the-badge&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjI0IiBoZWlnaHQ9IjI0Ij48ZyBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgc3Ryb2tlLXdpZHRoPSIyIj48cGF0aCBkPSJNMTIgMTloOCIvPjxwYXRoIGQ9Im00IDE3IDYtNi02LTYiLz48L2c%2BPC9zdmc%2B&logoColor=white"></a>
  <a href="FloorCutTree.java"><img alt="Source" src="https://img.shields.io/badge/Source-1E2A38?style=for-the-badge&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjI0IiBoZWlnaHQ9IjI0Ij48ZyBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgc3Ryb2tlLXdpZHRoPSIyIj48cGF0aCBkPSJtMTYgMTggNi02LTYtNiIvPjxwYXRoIGQ9Im04IDYtNiA2IDYgNiIvPjwvZz48L3N2Zz4%3D&logoColor=white"></a>
  <a href="https://mertkayacs.com/?utm_source=github&utm_medium=readme&utm_campaign=FloorCutTree-repo&utm_content=portfolio-badge"><img alt="Portfolio" src="https://img.shields.io/badge/Portfolio-1E2A38?style=for-the-badge&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjI0IiBoZWlnaHQ9IjI0Ij48ZyBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgc3Ryb2tlLXdpZHRoPSIyIj48Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIxMCIvPjxwYXRoIGQ9Ik0xMiAyYTE0LjUgMTQuNSAwIDAgMCAwIDIwYTE0LjUgMTQuNSAwIDAgMCAwLTIwTTIgMTJoMjAiLz48L2c%2BPC9zdmc%2B&logoColor=white"></a>
</p>

FloorCutTree models a cut floorplan, which is a rectangle divided by horizontal and vertical cuts into smaller rooms. Each room is a node in a binary tree. After you assign widths and heights to the rooms, compact finds the minimum width and height of every room that contains smaller rooms. A driver program runs directives from a text file, and display prints the tree.

---

## Why FloorCutTree

The program turns a floor plan into a tree and works out the smallest layout.

|  |  |
|---|---|
| <img src="docs/assets/readme/icons/scissors-line-dashed.svg" width="18" height="18" alt=""> **Cuts as tree nodes** | Each cut splits one room into two. Horizontal and vertical cuts are separate operations on a binary tree. |
| <img src="docs/assets/readme/icons/file-input.svg" width="18" height="18" alt=""> **Scripted input** | [FloorCutTreeDriver.java](FloorCutTreeDriver.java) reads one directive per line from a text file named test-hw3.txt. |
| <img src="docs/assets/readme/icons/boxes.svg" width="18" height="18" alt=""> **Layered tree classes** | FloorCutTree extends LinkedBinaryTree, which builds on the Tree, BinaryTree and Position classes in the same folder. |

## Features

**Directives**

| Directive | What it does |
|---|---|
| `create-root L` | Creates the root room with label L. |
| `cut-h V L1 L2` | Cuts room V horizontally into rooms L1 and L2. |
| `cut-v V L1 L2` | Cuts room V vertically into rooms L1 and L2. |
| `assign-w L N` | Sets the width of room L. |
| `assign-h L N` | Sets the height of room L. |
| `compact` | Computes the minimum size of every room that contains smaller rooms. |
| `display` | Prints the tree in order, one node per line, with the depth shown as dots. |
| `quit` | Stops the program. |

## Quick start

```sh
javac *.java
java FloorCutTreeDriver
```

Put the directives in a file named `test-hw3.txt` in the same folder, one per line, with the parts separated by spaces or tabs. The bundled test-hw3.txt is a sample script, and running the driver prints the tree after each display directive.

### Requirements

- A Java JDK. The repository does not pin a version.

## FAQ

<details>
<summary><b>What is a cut floorplan?</b></summary>

A rectangle divided by horizontal and vertical cuts into smaller rooms.
</details>

<details>
<summary><b>What does compact do?</b></summary>

It finds the minimum width and height of the rooms that contain smaller rooms.
</details>

<details>
<summary><b>Where does the input come from?</b></summary>

From test-hw3.txt in the working folder. The file name is fixed in the driver.
</details>

If FloorCutTree is useful to you, a ⭐ helps other people find it.

## License

[GPL-3.0](LICENSE).

[![views](https://hits.sh/github.com/mertkayacs/FloorCutTree.svg?view=today-total&style=flat-square&label=views&color=A9762B&labelColor=1E2A38)](https://github.com/mertkayacs/FloorCutTree)
