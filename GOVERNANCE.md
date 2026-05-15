# Governance Model

## 1. Current Stage: Benevolent Dictator for Life (BDFL)
The project is initiated and led by **AonzOG**, who acts as the BDFL for the project. The BDFL has final decision-making authority on technical direction, merges, and disputes. This ensures rapid progress while the community is small.

## 2. Transition to Community Steering Council
Once the project reaches **Phase 1 completion** (first multimodal model released), governance will transition to a **Steering Council** made up of core contributors elected by the community and lead the the BDFL. The BDFL will then become a regular member with historical weight.

## 3. Working Groups & Domains
Contributors will self-organize into these groups, each with a lead:

| Working Group | Responsibilities |
|---------------|------------------|
| **Data & Curation** | Collecting, cleaning, deduplicating, and annotating multimodal data. |
| **Infrastructure & Compute** | Setting up distributed training, managing donation grid, cloud orchestration. |
| **Model Architecture & Training** | Developing model components, encoders/decoders, AutoResearch, running experiments. |
| **Evaluation & Safety** | Defining benchmarks, red-teaming, bias audits, and releasing evaluation reports. |
| **Community & Documentation** | Onboarding, tutorials, communication (Discourse/Discord), and maintaining the website. |

Working group leads are appointed by the BDFL initially, later elected by group members.

## 4. Decision-Making Process (RFC)
- Any significant change (architectural, data policy, governance) must be proposed via a **Request for Comments (RFC)** document in the `rfcs/` directory.
- The RFC is discussed in the open for at least 14 days.
- Final decision rests with the BDFL (or later, the Steering Council) after weighing community feedback.
- Minor changes (bug fixes, doc updates) follow standard pull request process with review from relevant group.

## 5. Contributor License Agreement (CLA)
All contributors by contributing into this project subscribe to a CLA (individual or corporate) granting the project a perpetual, worldwide license to use their contributions under the project’s license (LICENSE.md). This keeps the project’s IP clean.

## 6. Code of Conduct
We adopt the Contributor Covenant Code of Conduct. Harassment, trolling, or unethical behaviour will result in removal from the community.
