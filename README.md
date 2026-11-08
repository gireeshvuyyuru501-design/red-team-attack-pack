# Red-Team Attack Pack

Offline AI response safety evaluation starter. Uses **synthetic adversarial prompt/response fixtures**, with deterministic heuristic checks for obvious secret exposure, instruction-override phrases, and refusal indicators. No API keys or external services required.

## Run

```bash
python -m unittest discover -s tests -v
python red_team.py
```

Produces `red_team_report.json` with case-level results.

## Scope and limitations

- These checks are **heuristics**, not a real LLM red-team benchmark or a safety certification.
- `passed` means a fixture satisfied simple pattern/refusal checks; false positives and false negatives are possible.
- Synthetic fixtures intentionally include unsafe example *responses* for testing. Never put actual secrets in fixture files.
- Future improvements: live Gemini/OpenAI model adapters, external benchmark datasets, manual adjudication, severity taxonomy, false-positive review, attack success rate and confidence intervals.
