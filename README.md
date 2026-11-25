# Describing Search in Negotiations

Scenario materials for the negotiation app and a guide to the exploratory pilot library.

## App materials

- Vacation planning with [two parties](scenario_2_party.json) and [five parties](scenario_5_party.json)
- Shared office with three parties in the [Easy](shared_office_3p_easy.json) and [Hard](shared_office_3p_hard.json) versions
- [Shared-office walkthrough](shared_office_3p_scenario.json) and [survey configuration](narative_survey.yaml)

The pilot library associates each group with the scorecards saved for its collection. Use the library’s matrix IDs to check the version used in a particular pilot.

## Exploratory pilot library

The research team’s private OneDrive project is **Exploratory pilot data**. Open `Browse.html` for the dataset index, `Pilot_Catalog.xlsx` for counts and agreement rates, or `Data_Dictionary.html` for column definitions. The progress tracker documents source coverage, including historical extracts, transcript gaps and Prolific matches.

Tables are pooled by negotiation family. Filter `dataset_id` for a specific collection. `group_id` identifies the negotiation and `matrix_id` identifies the payoff table associated with it.

| File | Unit and join |
|---|---|
| `groups.csv` | One row per negotiation group. Join on dataset and group ID. |
| `participants.csv` | One row per recorded seat. Includes available survey fields, a keyed participant pseudonym, and transcript links. |
| `offers.csv` | One row per saved proposal. Join on dataset, group and offer number. |
| `offer_members.csv` | One row per proposal and recorded seat. Contains the seat’s saved votes and offered points. |
| `Payoff_Matrices.json` | Scorecards and role materials. Join by matrix and role-material IDs. |

The group and participant tables also contain ordered JSON offer histories. Group histories carry issue changes, vote counts, joint and seat payoffs, and distance to the nearest bargaining-zone offer where it can be computed. Participant histories follow the same sequence from one seat’s perspective. Votes reflect the last saved response on each proposal. Blank values mark missing or unscorable observations.

In the payoff JSON, each matrix contains cards in seat order. Each card lists options by issue. A proposal’s option number is a zero-based index in that issue’s option list. Add the selected option scores to obtain the offer’s points for the seat.

Group demographic summaries include response counts. Same-category measures require a response from every assigned member. Gender identity and sex use their corresponding survey fields.

## Replication materials

The theory and main-study replication code is maintained in the [Search Complexity repository](https://github.com/SamQuinto/Search-Complexity).
