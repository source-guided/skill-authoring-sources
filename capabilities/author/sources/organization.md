# Organize a source by responsibility

Apply the current client's source participation contract, discovered through this source's contract reference. This guide explains how to choose a useful content structure; it does not prescribe domain names or a fixed directory template.

## Choose the owner before the document name

Identify the responsibilities a reader needs to enter independently. Reuse an existing domain or capability area when it owns the material. Within that area, separate questions and evidence, policies and specifications, and verification records only where their purposes or maintenance differ. A question answered by a stakeholder belongs with the affected subject, not in a perpetual root-level `questions.md` spanning every subject. Preserve a meeting record that covers several subjects in one evidence location and refer to its relevant sections from those subjects instead of duplicating the record.

Keep source-wide introduction, ownership and administrative metadata at the root. A genuinely cross-cutting overview can remain there as an entry, but it should route to detail owned by the areas. Creating `docs/` and putting every substantive document directly inside it does not establish those owner areas.

## Repeat the split-or-keep decision within each area

Treat a domain folder as another place to inspect responsibility, not as proof that its contents are already organized. For every affected area, ask what a reader comes to decide or change and which documents support that same task.

- Keep peer questions, specification and verification documents when they describe the same policy or workflow and change together. Their different document types alone do not justify more directories.
- Split into child areas when the responsibilities can be governed or changed independently. Assess ownership, input/output contracts, complete lifecycles and reasons to change together; different fields or consecutive steps of one lifecycle do not by themselves establish independent responsibilities. Move the relevant questions, rules, specification and evidence together to the child that owns them. Repeated subject sections across the peer documents are a useful place to find hidden subresponsibilities.
- Keep a common contract, vocabulary or evidence record in its authoritative parent or shared owner. Children reference it; do not copy it into every child or make all shared material a new global bucket.
- Stop when another split would scatter one coherent decision across fragments without improving ownership or retrieval. A large focused document may need headings or a contents section rather than new domains, and a short document can still mix independent responsibilities.

Mixed depth is expected. For example, reservation handling may eventually need separate ordinary and recurring workflows if they have independent policies and lifecycle, while a nearby inventory lookup remains a leaf with a specification and checks. Do not add such branches unless the real task contains those distinctions. A parent may have both shared documents and child areas.

Before accepting a leaf, try a concrete change from that area: identify which question, policy/specification and evidence must change together. If changing one independent subject requires searching unrelated sections of several broad documents, review a child-area split. Conversely, if understanding a single rule requires hopping through artificial one-paragraph directories, merge those fragments under their actual owner. Record the material split/keep rationale in the work review; do not generate a mandatory rationale file in every folder.

## Give both content and references a useful hierarchy

For a service with distinct inventory and reservation responsibilities, one possible shape is:

```text
references/
  index.json
  inventory/index.json
  reservations/index.json
sources/
  inventory/
    questions.md
    specification.md
  reservations/
    questions.md
    policy.md
    verification.md
```

The root reference exposes area entries and source-wide information. For filesystem sources, keep each area's index inside its own reference directory rather than collecting sibling `<area>.json` files at the reference root. Area indexes expose their own documents and any meaningful child areas. The two trees need not match path-for-path: use deeper branches where an area has distinct responsibilities, and keep a small focused area shallow. Never create empty placeholder branches to imitate this example. Existing source-local capabilities may continue to own their material under `capabilities/<capability>/`; remote stores may use grouped documents or pages instead of directories.

Reference entries describe where relevant content can be found. They do not contain the content. Relate areas through references when a task needs another owner; do not copy the other owner's policy or centralize every leaf in the root index. Follow an area's entry to find its detailed sources.

## Extend and review

For a new question, decision or specification, choose its owner area first and repeat the split-or-keep decision along the affected branch. Update the existing authoritative document or add a focused document there, then update the area's discovery metadata. If a former leaf now contains independently maintained responsibilities, split it and update incoming references and ordinary document links together. Preserve stable unrelated branches; do not reorganize the entire source for every small addition.

Validate the reference graph and publication inventory with the current client's source validator. Then inspect actual reader paths: can someone find the material for one responsibility without reading unrelated areas, and can they follow a dependency to the other owner? Confirm that questions retain their unanswered/answered status and source evidence after moves. Passing the structural validator alone does not demonstrate that the chosen responsibilities are useful.
