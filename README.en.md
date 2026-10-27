# LE PROMPTEUR — English overview

A teleprompter by Eric Mager — LAB, currently a 0.1.0 preview. Paste or import UTF-8 text, adjust the reading speed, add chapter headings with `##`, and add pauses such as `[pause 2s]`. The Studio panel lets you associate an image and notes with a passage. Images and notes are kept for manual reassignment when the text changes ambiguously.

Use **Projets → Exporter une sauvegarde** to export a portable JSON copy including images. Importing it creates a new project. Browser data can be cleared, so keep a backup. Imported content stays in the browser during ordinary use; no account is needed.

To run this preview locally, use `python -m http.server 8765 --bind 127.0.0.1` in this folder and open `http://127.0.0.1:8765/`. The interface is currently in French. Cross-browser, touch, interruption, long-file and release validation remain incomplete.
