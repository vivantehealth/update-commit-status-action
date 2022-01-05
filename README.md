# repo-name

To make this action available to other repos, it needs to be `internal` visiblity, and "Accessible from repositories in the 'vivantehealth' organization" set in [Settings->Actions](https://github.com/vivantehealth/terraform-plan-action/settings/actions)

Suggested use:

```yaml
jobs:
  run:
    name: Run
    runs-on: ubuntu-latest
    steps:
      - name: Update commit status failure
        if: ${{ failure() }}
        uses: vivantehealth/update-commit-status-action@v0
        with:
          state: "failure"
          context: ${{ github.workflow }}
```
