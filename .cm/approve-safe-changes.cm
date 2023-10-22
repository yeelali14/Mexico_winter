# -*- mode: yaml -*-
automations:
  safe_changes:
    # Triggered for any changes that only affect formatting, documentation, tests, or images
    if:
      - true
    # Apply a safe change label, approve the PR and explain why in a comment.
    run: 
      - action: add-label@v1
        args:
          label: 'safe-change'
      - action: merge@v1
        args:
          wait_for_all_checks: true

# These custom expressions are used in the safe_changes automation
is:
  formatting: {{ source.diff.files | isFormattingChange }}
  docs: {{ files | allDocs }}
  tests: {{ files | allTests }}
  image: {{ files | allImages }}
