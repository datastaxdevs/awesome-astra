# Create an Astra Token

[🏠 Back to Reference List](../README.MD)

> The Astra token creation procedure is also described in the [reference documentation](https://docs.datastax.com/en/astra/docs/manage-application-tokens.html)

## Prerequisites

- You should have an [Astra account](http://astra.datastax.com/)

## Procedure

### ✅ Step 1 : Open the Organization settings panel

On the top left hand corner locate the panel `Current Organization` with your email address. Use the chevron down **&#8964;** to open the menu and pick `Organizations Settings`

<img src="img/astra-create-token-1.png" />

### ✅ Step 2: Open the token management page

On the new page, select `Token Management` in the menu. Then use the `Select Roles` combo to select `Organization Administrator` role. This is the administrator of your tenant with all permissions.

<img src="img/astra-create-token-2.png" />

### ✅ Step 3: Save the token as a CSV. 

The values of `clientSecret` and `token` will not be shown to you later for security reasons. Do not share those values and never commit them on github.

<img src="img/astra-create-token-3.png" />

**👁️ Walkthrough**

<img src="img/astra-create-token.gif" />

You can use the clipboard icons in from of each parameter to put them in the clipboard and be copied elsewhere

<img src="img/astra-create-token-4.png" />

