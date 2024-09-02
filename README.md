# Sending the result of the actions as a Slack message

# Usages

```yaml
      - name: If Actions Failure
              if: ${{failure()}}
              run: echo "ACTIONS_STATUS=Failure" >> $GITHUB_ENV

            - name: If Actions Success
              if: ${{success()}}
              run: echo "ACTIONS_STATUS=Success" >> $GITHUB_ENV

            - name: Send Message
              if: ${{always()}}
              uses: cloudcoke/slack_actions@v1
              with:
                  status: ${{env.ACTIONS_STATUS}}
                  slack-webhook-url: ${{secrets.SLACK_WEBHOOK_URL}}
```
