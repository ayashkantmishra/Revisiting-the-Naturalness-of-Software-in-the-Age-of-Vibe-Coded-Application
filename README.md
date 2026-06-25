# Revisiting the Naturalness of Software in the Age of Vibe-Coded Applications

Reproducibility artifacts for the paper *"Revisiting the Naturalness of
Software in the Age of Vibe-Coded Applications"* (ISEC 2027).

This repository contains the repository index, analysis outputs, and figures
for our study. The cleaned source-code corpora are hosted separately on Google
Drive (link below) due to size.

---

## 1. What this study did, in one paragraph

We compare three corpora — human-written code, vibe-coded (AI-assisted) code,
and natural-language text — to test whether vibe-coded software is as
"natural" (statistically predictable) as human code. We measure naturalness two
ways: n-gram cross-entropy (token-level predictability) and CodeBERT embedding
geometry (where each corpus sits in representation space), across nine
programming languages. The repositories analyzed are indexed in
`Repo_information.xlsx`.

---

## 2. Repository contents

| File | Description |
|------|-------------|
| `Repo_information.xlsx` | Index of all source repositories used (see §3). |
| `Figure_1_Corpus_File_Distribution_by_Language.png` | File counts per language per corpus. |
| `Figure_2_PCA_SentenceBERT_Embeddings.png` | PCA of Sentence-BERT embeddings (robustness check). |
| `Figure_3_RQ1_Mean_CrossEntropy_by_Corpus.png` | Mean cross-entropy per corpus (RQ1). |
| `Figure_4_RQ2_PCA_CodeBERT_Embeddings.png` | PCA of CodeBERT embeddings (RQ2, primary). |
| `Figure_5_RQ2_PCA_SentenceBERT_Embeddings.png` | PCA of Sentence-BERT embeddings (RQ2, robustness). |
| `Figure_6_RQ3_Mean_CrossEntropy_Heatmap_Language.png` | Per-language cross-entropy, human vs vibe (RQ3). |
| `Figure_7_RQ3_Cliffs_Delta_Effect_Size_by_Language.png` | Per-language effect sizes (RQ3). |
| `Figure_8_RQ2_tSNE_CodeBERT_Embeddings.png` | t-SNE of CodeBERT embeddings (RQ2, paper Figure 3). |
| `Figure_9_Vocabulary_Diversity_TypeTokenRatio.png` | Type-token ratio per language per corpus. |

---

## 3. The repository index (`Repo_information.xlsx`)

Two sheets list every repository in the study. Repositories were collected from
public GitHub. **Human-coded** repositories (48, IDs `H001`–`H048`) are
established open-source projects confirmed to contain no AI-generation claims.
**Vibe-coded** repositories (53, IDs `V001`–`V053`) are projects whose own
authors declare them to be AI-assisted / vibe-coded.

**Shared columns (both sheets):**

| Column | Meaning |
|--------|---------|
| Repo ID | Internal identifier (`H###` / `V###`). |
| Repo Name | GitHub `owner/name`. |
| Full URL | Direct link to the repository. |
| Owner | Repository owner. |
| Language Group | Primary language family used for corpus grouping. |
| Major Language | Dominant language of the repository. |
| Framework / App Type | Short description of what the project is. |
| Age (Created Date) | Repository creation date. |
| Stars | Approximate star count at collection time. |
| License | Declared license (`Not specified` where none is given). |

**Human sheet only:**
- *No AI-Generation Mention (Confirmed)* — evidence that the project does not
  claim AI generation, supporting its use as a human-authored baseline.

**Vibe sheet only:**
- *Self-Declaration Quote* — the author's own statement that the project is
  vibe-coded / AI-assisted.
- *Evidence Link* — direct link to that statement (README, commit, or description).
- *AI Tool Named* — the AI assistant named by the author, where stated
  (`Other` / `unspecified` where the author confirms AI use without naming a tool).

---

## 4. Mapping paper claims to artifacts

Every quantitative claim in the paper can be traced to a figure here or to a
table in the paper itself.

| Paper element | Artifact |
|---------------|----------|
| RQ1 — cross-entropy by corpus (Table 2, §4.1) | `Figure_3_RQ1_Mean_CrossEntropy_by_Corpus.png` |
| RQ2 — embedding geometry, primary (Figure 3, §4.2) | `Figure_8_RQ2_tSNE_CodeBERT_Embeddings.png`, `Figure_4_RQ2_PCA_CodeBERT_Embeddings.png` |
| RQ2 — robustness check (§4.2) | `Figure_2_…`, `Figure_5_RQ2_PCA_SentenceBERT_Embeddings.png` |
| RQ3 — per-language gap (Table 3, Figure 4, §4.3) | `Figure_6_RQ3_…_Heatmap_…`, `Figure_7_RQ3_Cliffs_Delta_…` |
| Corpus statistics (Table 1, §3.1) | `Figure_1_Corpus_File_Distribution_…`, `Figure_9_…_TypeTokenRatio…` |
| Repositories analyzed (§3.1) | `Repo_information.xlsx` |

---

## 5. Data availability

- **This repository:** repository index + analysis outputs + figures.
- **Cleaned corpora:** the preprocessed, balanced source-code files used in all
  experiments are hosted on Google Drive: `<DRIVE_LINK>`

---

## 6. Notes on reproducibility and scope

- **Repository → file counts.** The 48 human and 53 vibe repositories were
  cloned and expanded into the file-level corpora analyzed in the paper
  (22,258 human and 4,653 vibe source files before balancing; 4,439 each after
  language-stratified balancing). See paper §3.1 for the full cleaning and
  balancing procedure. The cleaned files themselves are on the Google Drive above.
- **Vibe-coded labels.** Vibe-coded repositories are identified by author
  self-declaration. As noted in the paper's Threats to Validity, these labels
  are inherently noisy; a repository may mix human-written and AI-generated
  code. This label noise biases comparisons toward the null, so the reported
  human–vibe differences are conservative.
- **Repository state.** Repository metadata reflects collection time and
  repositories may have changed since. The `Full URL` column allows
  re-retrieval; for exact reproduction, pin each repository to a specific commit.

---

## 7. Ethics

All data is drawn from publicly available GitHub repositories. No private data,
no human-subjects interaction, and no personally identifying information beyond
public repository ownership is involved. Repository licenses are recorded in
`Repo_information.xlsx`; users of this dataset should honor the individual
licenses of the referenced repositories.

---

