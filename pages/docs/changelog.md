---
# Copyright (C) 2020 Julian Valentin, LTeX Development Community
#
# This Source Code Form is subject to the terms of the Mozilla Public
# License, v. 2.0. If a copy of the MPL was not distributed with this
# file, You can obtain one at https://mozilla.org/MPL/2.0/.

title: "Changelog"
permalink: "/docs/changelog.html"
sidebar: "sidebar"
toc: false
---

## 7.0.0 — “The Workspace Solution” (September 13, 2020)

- Change scope of [`ltex.dictionary`](settings.html#ltexdictionary), [`ltex.disabledRules`](settings.html#ltexdisabledrules), and [`ltex.enabledRules`](settings.html#ltexenabledrules) to `application`; these are now user-specific settings that can only be configured in user settings
- Add settings [`ltex.workspaceDictionary`](settings.html#ltexworkspacedictionary), [`ltex.workspaceDisabledRules`](settings.html#ltexworkspacedisabledrules), and [`ltex.workspaceEnabledRules`](settings.html#ltexworkspaceenabledrules) with `window` scope to amend the corresponding user-specific settings; these are workspace-specific settings that should be configured in workspace settings
- Add settings [`ltex.workspaceFolderDictionary`](settings.html#ltexworkspacefolderdictionary), [`ltex.workspaceFolderDisabledRules`](settings.html#ltexworkspacefolderdisabledrules), and [`ltex.workspaceFolderEnabledRules`](settings.html#ltexworkspacefolderenabledrules) with `resource` scope to amend the corresponding user-specific and workspace-specific settings; these are workspace-folder-specific settings that should be configured in workspace folder settings
- Change default of [`ltex.configurationTarget`](settings.html#ltexconfigurationtarget) for `addToDictionary` to `workspaceFolder`, i.e., by default, words will now be added to the workspace-folder-specific settings instead of the user-specific settings
- Rename `"global"` value for [`ltex.configurationTarget`](settings.html#ltexconfigurationtarget) to `"user"` (`"global"` is still supported, but deprecated)
- Remove deprecated settings `ltex.javaHome`, `ltex.performance.initialJavaHeapSize`, `ltex.performance.maximumJavaHeapSize`, `ltex.performance.sentenceCacheSize`, `ltex.*.dictionary`, `ltex.*.enabledRules`, and `ltex.*.disabledRules` (deprecation since 5.0.0)
- Update LanguageTool to 5.0.2 (see [LT 5.0.2 release notes](https://github.com/languagetool-org/languagetool/blob/v5.0.2/languagetool-standalone/CHANGES.md#502-2020-08-28))
- Fix skipping of YAML front matter (fixes [#104](https://github.com/valentjn/vscode-ltex/issues/104))

## 6.3.0 — “The Vowel Extraction” (August 22, 2020)

- Add support for `an` article when before a formula starting with a vowel (e.g., `an $n$-dimensional problem`, fixes [#92](https://github.com/valentjn/vscode-ltex/issues/92))
- Add support for `~/` and `~\` in settings (fixes [#99](https://github.com/valentjn/vscode-ltex/issues/99))
- Fix links to documentation in various places (readme, changelog, error messages, etc.)

## 6.2.0 — “The Command Isotope” (August 7, 2020)

- Add commands [`LTeX: Check current document`](https://valentjn.github.io/vscode-ltex/docs/commands.html#ltex-check-current-document) and [`LTeX: Check all documents in workspace`](https://valentjn.github.io/vscode-ltex/docs/commands.html#ltex-check-all-documents-in-workspace) (fixes [#84](https://github.com/valentjn/vscode-ltex/issues/84))
- Add commands [`LTeX: Clear diagnostics in current document`](https://valentjn.github.io/vscode-ltex/docs/commands.html#ltex-clear-diagnostics-in-current-document) and [`LTeX: Clear all diagnostics`](https://valentjn.github.io/vscode-ltex/docs/commands.html#ltex-clear-all-diagnostics)
- Add setting [`ltex.clearDiagnosticsWhenClosingFile`](https://valentjn.github.io/vscode-ltex/docs/settings.html#ltexcleardiagnosticswhenclosingfile)
- Skip front matter in Markdown
- Ignore more LaTeX preamble commands (e.g., `\automark`, `\color`, `\DeclareSIUnit`, `\directlua`, `\setuptoc`)
- Add support for German babel hyphenation commands `"-`, `""`, `"|`, `"=`, `"~`
- Use non-breaking space for `~`

## 6.1.1 — “The Space Saturation” (July 26, 2020)

- Fix another problem with spaces in paths when using LTeX LS on Windows (fixes [#80](https://github.com/valentjn/vscode-ltex/issues/80))

## 6.1.0 — “The babel Momentum” (July 26, 2020)

- Download Java 11 if only Java 8 is installed; LTeX support for Java 8 will end on November 1, 2020 (see [documentation](https://valentjn.github.io/vscode-ltex/docs/deprecation-of-java-8.html) and [#39](https://github.com/valentjn/vscode-ltex/issues/39))
- Add support for babel commands (see [documentation](https://valentjn.github.io/vscode-ltex/docs/advanced-features.html#multilingual-latex-documents-with-the-babel-package), fixes [#81](https://github.com/valentjn/vscode-ltex/issues/81))
- Fix problems with spaces in paths when using LTeX LS on Windows (fixes [#80](https://github.com/valentjn/vscode-ltex/issues/80))
- Update bundled AdoptOpenJDK JRE to 11.0.8+10
- Update some NPM dependencies

## 6.0.2 — “The Startup Congruence” (July 11, 2020)

- Make Windows startup script of LTeX LS (`ltex-ls.bat`) honor `JAVA_HOME` (fixes [#75](https://github.com/valentjn/vscode-ltex/issues/75))
- Relicense vscode-ltex under the Mozilla Public License Version 2.0
- Update some NPM dependencies

## 6.0.1 — “The Freeze Paradox” (July 2, 2020)

- Fix freezes when checking German text by working around [languagetool-org/languagetool#3181](https://github.com/languagetool-org/languagetool/issues/3181) introduced by LanguageTool 5.0 (fixes [#68](https://github.com/valentjn/vscode-ltex/issues/68))

## 6.0.0 — “The Internationalization Proposition” (June 28, 2020)

- Update LanguageTool to 5.0 (see [LT 5.0 release notes](https://github.com/languagetool-org/languagetool/blob/v5.0/languagetool-standalone/CHANGES.md#50-2020-06-27))
- Add support for internationalized user interface of LTeX
- Add German translations for user interface of LTeX
- Delay diagnostics at the current caret position (e.g., incomplete word or sentence) until the user has finished typing (fixes [#46](https://github.com/valentjn/vscode-ltex/issues/46))
- Add `enabled` to magic comments (fixes [#67](https://github.com/valentjn/vscode-ltex/issues/67))
- Add command [`LTeX: Report bug in LTeX`](https://valentjn.github.io/vscode-ltex/docs/commands.html#ltexreportbug) for reporting LTeX bugs from within VS Code
- Fix `\todo` couldn't be ignored (fixes [#63](https://github.com/valentjn/vscode-ltex/issues/63))
- Fix wrong language-dependent settings used for magic comments
- Fix add to dictionary and disable rule quick fixes using wrong language when used with magic comments
- Fix deprecation message for `ltex.performance.maximumJavaHeapSize` not shown
- Improve code quality of LTeX LS by fixing hundreds of Checkstyle, SpotBugs, and Checker Framework warnings
- Migrate LTeX LS from Gradle to Maven
- Update NPM dependencies
- Update Maven dependencies

## 5.0.2 — “The Disabling Submergence” (June 18, 2020)

- Fix `Disable rule` quick fix using wrong setting structure (fixes [#61](https://github.com/valentjn/vscode-ltex/issues/61))

## 5.0.1 — “The Acceptance Incursion” (June 7, 2020)

- Fix `Value is not accepted` warning when using [`ltex.disabledRules`](settings.html#ltexdisabledrules) or [`ltex.enabledRules`](settings.html#ltexenabledrules) (fixes part of [#44](https://github.com/valentjn/vscode-ltex/issues/44))
- Change badges in readme

## 5.0.0 — “The Rewrite Materialization” (June 1, 2020)

- Download LTeX Language Server on demand with all languages already included; this removes the need for language support extensions (fixes [#6](https://github.com/valentjn/vscode-ltex/issues/6))
- Download Java distribution on demand if no suitable Java installation has been found (fixes [#5](https://github.com/valentjn/vscode-ltex/issues/5))
- Adhere to [semantic versioning](https://semver.org/). This means that the version of LTeX is not tied to the version of LanguageTool anymore, as the version of LanguageTool is not a semantic version. LTeX 5.0.0 uses LanguageTool 4.9.
- Rename settings:
  - `ltex.<LANGUAGE>.dictionary` to [`ltex.dictionary`](settings.html#ltexdictionary) (object with `<LANGUAGE>` keys)
  - `ltex.<LANGUAGE>.disabledRules` to [`ltex.disabledRules`](settings.html#ltexdisabledrules) (object with `<LANGUAGE>` keys)
  - `ltex.<LANGUAGE>.enabledRules` to [`ltex.enabledRules`](settings.html#ltexenabledrules) (object with `<LANGUAGE>` keys)
  - `ltex.javaHome` to [`ltex.java.path`](settings.html#ltexjavapath)
  - `ltex.performance.initialJavaHeapSize` to [`ltex.java.initialHeapSize`](settings.html#ltexjavainitialheapsize)
  - `ltex.performance.maximumJavaHeapSize` to [`ltex.java.maximumHeapSize`](settings.html#ltexjavamaximumheapsize)
  - `ltex.performance.sentenceCacheSize` to [`ltex.sentenceCacheSize`](settings.html#ltexsentencecachesize)
- Add support for external LanguageTool HTTP servers (fixes [#36](https://github.com/valentjn/vscode-ltex/issues/36))
- Add support for magic comments, enables changing the language in the middle of documents (fixes [#21](https://github.com/valentjn/vscode-ltex/issues/21))
- Check `\footnote` and `\todo` contents separately, preventing “double period” warnings (fixes [#42](https://github.com/valentjn/vscode-ltex/issues/42))
- Add support for more BibLaTeX citation commands, add support for plural dummies, add support for `\eg`, `\egc`, `\ie`, `\iec` (fixes [#43](https://github.com/valentjn/vscode-ltex/issues/43))
- Add visual feedback in status bar during startup and checks that take a long time
- Remove `null` types and default values from settings, use empty string/array/object instead (fixes [#41](https://github.com/valentjn/vscode-ltex/issues/41))
- Use proper server/client model for language server/client
- Make documentation more extensive, put it on own [website](https://valentjn.github.io/vscode-ltex/)

## 4.9.3 — “The Java Collapse” (May 7, 2020)

- Revert back to Java 8
- Remove support for external LanguageTool HTTP servers

## 4.9.2 — “The Server Renormalization” (May 6, 2020)

- Update required version of Java (now 11 or newer)
- Add support for external LanguageTool HTTP servers (fixes [#36](https://github.com/valentjn/vscode-ltex/issues/36))
- Add support for `\autoref`, `\pageref`, `\autopageref` (fixes [#37](https://github.com/valentjn/vscode-ltex/issues/37))

## 4.9.1 — “The Sentence Cache Acceleration” (May 1, 2020)

- Fix sentence cache was invalidated when a single ignore sentence rule was present (fixes [#29](https://github.com/valentjn/vscode-ltex/issues/29))
- Use thin non-breaking space for `\,` (fixes [#35](https://github.com/valentjn/vscode-ltex/issues/35))

## 4.9.0 — “The Update Alternative” (March 28, 2020)

- Update to LanguageTool 4.9 (see [LT 4.9 release notes](https://github.com/languagetool-org/languagetool/blob/v4.9/languagetool-standalone/CHANGES.md#49-2020-03-24))
- Update other Java dependencies
- Update npm dependencies
- Update required version of VS Code (now 1.39 or newer)
- Reduce file size of extension (omitting unneeded dependencies)
- Add usage instructions to readme

## 4.7.10 — “The French Capacitance” (March 12, 2020)

- Fix spelling errors for French dummies (fixes [#27](https://github.com/valentjn/vscode-ltex/issues/27))
- Fix `\dots` in math mode being interpreted as `...`
- Minor changes in readme, changelog, and package.json

## 4.7.9 — “The Markdown Resonance” (February 29, 2020)

- Update the Markdown parser flexmark-java to 0.60.2; this increases the speed of parsing Markdown
- Add possibility to ignore Markdown elements or replace them by dummy words via [`ltex.markdown.ignore`](settings.html#ltexmarkdownignore) and [`ltex.markdown.dummy`](settings.html#ltexmarkdowndummy) (fixes [#26](https://github.com/valentjn/vscode-ltex/issues/26))
- Ignore Markdown code blocks by default
- Replace auto-links and inline Markdown code with dummy words by default
- Fix match positions were sometimes off by one, especially in Markdown documents
- Rewrite `MarkdownAnnotatedTextBuilder`

## 4.7.8 — “The Multi-Diagnostic Equivalency” (February 16, 2020)

- Add support for R Sweave `.rnw` files (fixes [#22](https://github.com/valentjn/vscode-ltex/issues/22))
- Enable fixing multiple diagnostics at once (fixes [#23](https://github.com/valentjn/vscode-ltex/issues/23))
- Add `ltex.javaHome` setting to control the `JAVA_HOME` environment variable (PR [#24](https://github.com/valentjn/vscode-ltex/issues/24) by mpolitze)
- Add support for `\euro` (fixes [#25](https://github.com/valentjn/vscode-ltex/issues/25))
- Minor changes in readme

## 4.7.7 — “The Preview Perturbation” (November 23, 2019)

- Remove preview status from extension

## 4.7.6 — “The Java Thermalization” (November 10, 2019)

- Add `ltex.performance` settings to give users more control over Java's RAM usage
- Change default initial Java heap size to 64 MB
- Change default maximum Java heap size to 512 MB
- Change default sentence cache size from 10000 to 2000 sentences
- Rename logs, enable logging of client messages even if no folder is open
- Add more examples to readme

## 4.7.5 — “The Listing Collapse” (October 22, 2019)

- Enable ignoring environments such as `lstlisting` and `verbatim`
- Add [`ltex.environments.ignore`](settings.html#ltexenvironmentsignore) setting for defining own environments to ignore

## 4.7.4 — “The Disabling Allocation” (October 15, 2019)

- Add `disabledRules` and `enabledRules` settings (requires update of language extensions)
- Add `disable rule` quick fix
- Fix a bug where the `codeAction` request gets stuck in infinite loop
- Fix another `NullPointerException` for word2vec

## 4.7.3 — “The word2vec Erosion” (October 7, 2019)

- Fix null pointer error for word2vec quick fixes (fixes [#12](https://github.com/valentjn/vscode-ltex/issues/12))

## 4.7.2 — “The Message Dissection” (October 2, 2019)

- Add missing error message if legacy false friends could not be loaded

## 4.7.1 — “The Mother Tongue Factor” (October 2, 2019)

- Add [`ltex.additionalRules.motherTongue`](settings.html#ltexadditionalrulesmothertongue) setting to enable detection of false friends (fixes [#11](https://github.com/valentjn/vscode-ltex/issues/11))
- Change defaults for `ltex.additionalRules` settings from `""` to `null`

## 4.7.0 — “The Multi-Root Observation” (October 1, 2019)

- Update to LanguageTool 4.7 (see [LT 4.7 release notes](https://github.com/languagetool-org/languagetool/blob/v4.7/languagetool-standalone/CHANGES.md#47-2019-09-28))
- Support multi-root workspaces, all configuration settings except [`ltex.enabled`](settings.html#ltexenabled) are now resource-specific (fixes [#7](https://github.com/valentjn/vscode-ltex/issues/7))
- Save dictionary settings under full language short code (e.g., `en-US` instead of `en`). If you already have a dictionary under `ltex.en.dictionary` and use `en-US` as language (not `en`), you have to rename the settings name to `ltex.en-US.dictionary` (similarly for other languages).
- Remove diagnostics when a file is closed
- Prevent insertion of text in TikZ mode
- Add support for more commands such as `\newenvironment`, `\newgeometry`, and `\pagenumbering`

## 4.6.13 — “The Remote Permeability” (September 26, 2019)

- Fix language extensions not installable on remote machines (fixes [#8](https://github.com/valentjn/vscode-ltex/issues/8))
- Fix language server not reinitialized after a language extension has been installed (which was missing during initialization)

## 4.6.12 — “The Interpolation Entanglement” (September 25, 2019)

- Patch LanguageTool's `AnnotatedText` with linear interpolation to hopefully fix the `fromPos must be less than toPos` LT errors for good
- Fix `\footnote` in math mode messed up text mode and math mode
- Increase robustness in case locale or settings are not provided
- Ignore all brace and bracket arguments after `\begin{environment}` (`tabular`, `array`, etc.)
- Add support for some more commands and environments such as `\pagestyle` and `eqnarray`

## 4.6.11 — “The Infinite Loop Contraction” (September 23, 2019)

- Detect and prevent infinite loops in `LatexAnnotatedTextBuilder`
- Fix infinite loop with other line endings than `\n`
- Fix some more `fromPos must be less than toPos` LT errors
- Check for interrupts to avoid 100% CPU usage on timeout (this doesn't fix any bugs though)
- Add support for `\email`, `\href`, and `\verb|...|`
- Add support for more citation commands (`\citep`, `\citet`, etc.)
- Add support for float/theorem definition commands and starred sectioning commands

## 4.6.10 — “The Plaintext Decay” (September 18, 2019)

- Don't check plaintext files (fixes [#4](https://github.com/valentjn/vscode-ltex/issues/4))
- Fix `NullPointerException` if LanguageTool has not been initialized (fixes [ltex-ls#1](https://github.com/valentjn/ltex-ls/issues/1))

## 4.6.9 — “The Bundle Valuation” (September 8, 2019)

- Bundle Node.js modules to decrease number of files in the extension (this means a slight performance gain)

## 4.6.8 — “The Severity Manifestation” (September 7, 2019)

- Add setting [`ltex.diagnosticSeverity`](settings.html#ltexdiagnosticseverity) to control where and how the diagnostics appear
- Change default severity from `warning` to `info`
- Add possibility to ignore a LanguageTool rule in a sentence via quick fix
- Add setting [`ltex.configurationTarget`](settings.html#ltexconfigurationtarget) to control which `settings.json` to update when using one of the quick fixes
- More commands like `\PackageWarning` and `\addbibresource` are ignored
- Add support for `\url` and `\nolinkurl`
- Add support for more accents (`` \` ``, `\'`, `\^`, `\~`, `\"`, `\=`, `\.`, ...)
- Command names can now include `@` (this assumes that users don't write something like `\example@gmail.com` with a command `\example`, otherwise replace with `\example{}@gmail.com`)
- Ignore alignment argument of tabular environment

## 4.6.7 — “The Model Combustion” (September 2, 2019)

- Add possibility to use language model *n*-gram data, neural network model data, or word2vec model data
- `Add to dictionary` now always modifies global settings

## 4.6.6 — “The Timeout Theorem” (September 2, 2019)

- Fix `fromPos must be less than toPos` LT errors
- Localization of diagnostics, initially support of English and German
- Add timeout for `latex.AnnotatedTextBuilder`; unfortunately this only displays an error, but does not kill the process
- Add support for `\(`, `\)`, `\[`, `\]`
- Don't insert spaces before `\text` in display math

## 4.6.5 — “The Consistency Integration” (September 2, 2019)

- Make readme and package.json consistent
- Fix second arguments of `\(re)newcommand` not ignored

## 4.6.4 — “The Umlaut Expansion” (September 1, 2019)

- Ignore some commands often found in LaTeX preambles
- Support umlauts and eszett

## 4.6.3 — “The Version Interruption” (September 1, 2019)

- Fix deployed *.vsix needed Java 11, not 8

## 4.6.2 — “The vsce Minimization” (September 1, 2019)

- Don't include vsce in extension

## 4.6.1 — “The Badges Vortex” (September 1, 2019)

- Link badges in readme

## 4.6.0 — “The LTeX Resurgence” (September 1, 2019)

- Forked abandoned repository, rename to vscode-ltex
- Update to LanguageTool 4.6 (see [LT 4.6 release notes](https://github.com/languagetool-org/languagetool/blob/v4.6/languagetool-standalone/CHANGES.md#46-2019-06-26))
- Update other dependencies (vscode, vscode-languageclient, LSP, JUnit, Gradle)
- Implement simple LaTeX parser

## 3.8.0 (July 8, 2017)

- Update to LanguageTool 3.8 (see [LT 3.8 release notes](https://github.com/languagetool-org/languagetool/blob/v3.8/languagetool-standalone/CHANGES.md#38-2017-06-27))
- Update versioning to reflect LanguageTool versioning
- Remove preview flag since no blocker issues have been reported

## 0.0.4 (June 22, 2017)

- Add configuration to make extension opt-in by workspace thanks to [Faustino Aguilar](https://github.com/faustinoaq) ([PR #5](https://github.com/adamvoss/vscode-languagetool/pull/5)) (workaround for [Microsoft/vscode#15611](https://github.com/Microsoft/vscode/issues/15611))
- Language-support extensions are now detected through the Visual Studio Code API rather than file-path assumptions.  This is better practice and makes development of the extension easier.

## 0.0.3 (June 14, 2017)

- Fix checking of files when no folder was open
- Prevent virtual files, including those from the git scm provider, from being checked (fixes [#2](https://github.com/adamvoss/vscode-languagetool/issues/2))

## 0.0.2 (June 12, 2017)

- Allow any LanguageTool supported language to be used through the use of supplemental extensions
- Remove built-in English support

## 0.0.1 (June 3, 2017)

- Initial release
