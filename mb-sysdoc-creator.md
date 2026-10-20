---
title: "mb-sysdoc-creator"
doc-id: "mb-7db5cba3"
updated: "2026-10-20"
---

# mb-sysdoc-creator

Researches a skill or system against its issuer's authoritative specification, and writes or refreshes its four documents: config, reference, explainer and learnings. It is the only system that researches issuers and writes these documents.

**Governing specification:** `C:\mybizz\mybizz-config-docs\mb-sysdoc-creator\doc-suite-specification.md`. Every document written satisfies it. Nothing is drafted from memory of it.

---

## Invocation

- `/mb-sysdoc-creator (system-name)`, by the developer or by mb-config-manager.
- The developer may supply a description, files or links in the same message. These are leads to verify, never text to copy.
- `system-name` is the folder name. A system MyBizz built starts with `mb-`. If the name matches no existing folder, or breaks the `mb-` rule, confirm the name with the developer before anything else.

---

## Hard rules

1. **Verify live.** Never write a fact from supplied material alone when it can be verified. Where only the developer can run the check, give the exact command and wait for the real output.
2. **The issuer's specification for the installed version is the standard.** Record every standard value with a link to its exact source. A value with no source is an open item.
3. **Read the learnings first.** Read the system's learnings file in full before researching. Never propose a change that contradicts an entry without citing the entry and stating why.
4. **Run the cross-system check every run.** Check Cupcake rules, memory governor treatment, `security-global` principles, and related skills and sources. Report "none found" for any with no result.
5. **One fact, one home.** Follow the specification's tests for every line.
6. **Never blend confirmed and unverified.** An unverified fact is written as an open item, never as settled.
7. **Two approvals.** The developer approves the findings, then the drafts. Nothing is drafted before the first. Nothing is written before the second.
8. **Never install anything.** Never install, upgrade or update any system. A newer issuer release is reported as a finding, and the developer decides.
9. **On any block, stop.** When Cupcake or any policy blocks an action, report the exact block. Give the developer the exact grant line, in the form set in `mybizz-os-docs/operating-procedures/grant-paths.md`, with the narrowest folder or domain and the smallest count the work needs:
   - `mg-grant --path <folder> --count N` to write in a folder;
   - `net-grant --domain <domain> --count N` to reach a website.
   Wait for the developer. Never grant access to itself. Never work around a block.
10. **Write only inside the system's folder**, `C:\mybizz\mybizz-config-docs\{system}\`, and in its own learnings file. Never rename an existing document.
11. **Keep no record of its own runs.** Findings are given in chat. Git keeps history.
12. **Never commit.** The developer runs commit-all.

---

## Mode

Decided at Phase 0, never asked:

- **Create:** the folder does not exist, or holds none of the four documents. All four are written.
- **Refresh:** the folder holds at least one of the four. Each existing document is refreshed row by row. Each missing document is created. An existing document is rewritten whole only when it must be restructured to the specification, every fact in it has been marked carried, corrected or retired, and the developer has approved the full draft.

---

## Phases

### Phase 0 — Locate

1. Confirm the specification exists. If not, STOP and report.
2. Read this skill's own learnings, `C:\mybizz\mybizz-config-docs\mb-sysdoc-creator\sysdoc-creator-learnings.md`, and apply them.
3. Find the folder `C:\mybizz\mybizz-config-docs\{system}\`. List which of the four documents exist, found by their endings: `-config.md`, `-reference.md`, `-explainer.md`, `-learnings.md`.
4. Set the mode.
5. **Refresh:** read every existing document in full, the learnings first.

### Phase 1 — Intake

Read everything the developer supplied in full. Open every link supplied. Request `net-grant` where a site is blocked.

### Phase 2 — Research

1. **Issuer and version.**
   - Name the issuer. For a system MyBizz built, the issuer is MyBizz, and the standard is its source files. Its repository is listed in `mybizz-os-docs/os-reference-docs/repo-organization.md`.
   - Read the installed version live, or give the developer the exact command.
2. **Authoritative sources.**
   - Find the issuer's official documentation, source repository, release notes and configuration schema for the installed version.
   - Note the newest issuer release. If it is newer than the installed version, record it as a finding: new version, what its release notes say changes or breaks, and which learnings entries it affects.
3. **Settings.** For every setting:
   - the issuer standard, with its exact source link;
   - the MyBizz value, verified live;
   - whether they differ. A difference is either justified by a learnings entry (name its ID), or reported as unjustified, with a proposed learnings entry or a proposed correction.
4. **Checks.** For every setting, the installed version, and whether the system works: the exact method to check it live, and whether the agent or the developer runs it.
5. **Cross-system check.** Hard rule 4.
6. **GBrain.** Search several times, varying terms: the system's name, its function, and related terms.
7. **Provenance.** Track every fact as confirmed live, confirmed through GBrain, unverified from a source, or stated by the developer.
8. **Refresh:** compare every row and section of the existing documents with the research. List each difference.
9. **Other files.** For every file in the folder that is not one of the four and not a working file listed in the config, place each fact that is still true in the document that owns it, and drop each fact that is no longer true. At Phase 7, name each emptied file. The developer deletes it.

### Phase 3 — Report, first approval

Present, before drafting:

- **Create:** the findings, sorted by the document they belong in.
- **Refresh:** a numbered change list. Each item gives the document, the row or section, the current text, the proposed text, and the source.
- Unverified facts, flagged.
- The cross-system check results, including every "none found".
- Any newer issuer release (Phase 2, step 2).
- Proposed learnings entries.
- Any command the developer must run before drafting can continue.

Stop and wait. The developer approves, corrects (apply exactly as given), asks for more research, or rejects (return to Phase 2 with the gap named).

### Phase 4 — Draft

- **Create:** draft all four documents. The learnings document holds the approved entries, or only its empty table.
- **Refresh:** draft only the approved changes, plus any missing document.
- Run every line through its document's placement test in the specification. Move any misplaced line to the document that owns it.

### Phase 5 — Present, second approval

Present the drafts or changes. The developer approves, corrects (apply exactly as given), or rejects a document (return to Phase 4 for that document only).

### Phase 6 — Apply

- Write inside the system's folder only. Request `mg-grant` for the folder if blocked.
- **Create:** write the four documents, each named `{folder}{ending}`.
- **Refresh:** change only the approved rows and sections in place, or write a whole document where its restructure was approved. Create any missing document, named with the same start as the documents already in the folder.

### Phase 7 — Close

1. If the run taught something about doing this job well, propose an entry for this skill's own learnings. Write it only if approved.
2. Report what was written, document by document.
3. Give the revoke line for any grant still open: `mg-revoke --path <folder>` or `net-revoke --domain <domain>`.
4. Remind the developer to commit with commit-all.

---

## Completion status

- **DONE:** both approvals given in this run, and every approved change written.
- **BLOCKED:** waiting on a developer-run command's output, or on a confirmed system name.
- **PERMISSION_REQUIRED:** a policy blocked an action. State the block and the grant line needed.
- **REPORT_REJECTED:** the developer rejected the findings. State the gap to research.
- **DRAFT_REJECTED:** the developer rejected one or more documents. State which and why. Redraft only those.

Never mark DONE without both approvals from this run, or with a document that has not passed its placement test.
