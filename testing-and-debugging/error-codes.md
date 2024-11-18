---
description: MindStudio Error Codes and what they mean.
---

# Error Codes

| Error                                                                                      | Details                                                                                                      |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| `Failed to fetch checkout session URL. Please try again.`                                  | Appears when Stripe does not return a checkout URL when initiating payment for subscription.                 |
| `StripeCardError`                                                                          | Appears when there is a card error during Stripe checkout. This error is provided by Stripe directly.        |
| `Invalid user ID. Unable to load user profile.`                                            | Error when loading a user profile.                                                                           |
| `This account has been banned.`                                                            | Appears when a trying to load a user account that has been banned.                                           |
| `Please enter a valid email address.`                                                      | Appears during signup or changing email.                                                                     |
| `Please enter a valid password.`                                                           | Appears during signup or changing password.                                                                  |
| `An account with this email address already exists.`                                       | Appears while attempting to create a new account with an email that has already been used.                   |
| `An account with this email address already exists. Use {signup_provider} to log back in.` | Error during signup if a user tries to login via email, and that email was used for a Google or Apple login. |
| `Username must be between 2 and 30 characters.`                                            | Error when attempting to change a username.                                                                  |
| `Username already exists.`                                                                 | Error during sign up or when attempting to change a username.                                                |
| `Password can not be changed. This account was created using Google or Apple sign in.`     | Appears when trying to change the password but the account was not created via email signup.                 |
| `Unable to reset password. Please try again.`                                              | Invalid token when trying to reset a password (could happen if the reset url was copied incorrectly).        |
| `Outdated request. Try to reset the password again.`                                       | Error when resetting the password but the token expired.                                                     |
| `Email verification failed. Missing verification token.`                                   | Error when verifying an email.                                                                               |
| `Outdated request. Try to resend the verification email.`                                  | Error when verifying an email but the token expired.                                                         |
| `The email is already verified.`                                                           | Error when email has already been verified.                                                                  |
| `API key or app ID is invalid. Please check your embed configuration.`                     | Appears when an invalid api key or app id set in the embed code.                                             |
| `The domain ${domain.toLowerCase()} is not authorized to embed this app.`                  | Appears when domain has not been authorized for the embed.                                                   |
| `Unable to save draft. Please reload and try again.`                                       | Appears when saving a draft.                                                                                 |
| `LLM Error: {error}`                                                                       | Error from an LLM. Message is provided by the LLM provider via an external api.                              |
| `Application can not be found.`                                                            | Appears when the app ID is non-existent or the application was deleted.                                      |
| `You are out of usage credits. Contact your workspace owner to restore service.`           | Appears when user is out of credits.                                                                         |
| `{model}: Invalid temperature`                                                             | Appears when the model temperature is invalid.                                                               |
| `{model}: Invalid response size`                                                           | Appears when the model repsonse size is invalid.                                                             |
| `{model}: There was an error processing your message`                                      | Appears when an LLM response fails.                                                                          |
| `{model}: {message}`                                                                       | This message is sent by the model provider via an external api.                                              |
| `{model}: Prompt is too large: ${promptTokenCount} / ${MODEL_MAX_TOKENS} tokens`           | Appears when the message exceeds the max token size.                                                         |
| `{model}: Empty response`                                                                  | Happens when there is an empty response from an LLM.                                                         |
| `Your Data Source is too large. Data Sources can not exceed 500k words.`                   | Appears when attempting to upload a data source that exceeds the file size.                                  |
| `Error while querying data source. Please try again.`                                      | Appears when an LLMs data query fails.                                                                       |
| `Error while scraping provided URL. Please try again.`                                     | Appears when URL is invalid or URL is not able to scraped.                                                   |

