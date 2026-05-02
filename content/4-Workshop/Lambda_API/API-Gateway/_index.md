---
title: "Set up API Gateway"
weight: 2
chapter: false
pre: " <b> 4.3.2 </b> "
---

We create a REST API with two routes and attach a Cognito JWT Authorizer to protect `GET /songs`.

---

## 1. Create the API

1. Go to **API Gateway Console** → **Create API**
2. Select **REST API** → **Build**

![Create API](/images/workshop/AG1.png)

3. Configure:
   - **API name:** `workshop-api`
   - **Endpoint type:** Regional

![Configure API](/images/workshop/AG2.png)

4. Click **Create API**. You will see the root resource `/`.

![Root resource](/images/workshop/AG3.png)

---

## 2. Create resources and methods

### /login resource

1. Select the root `/` → **Actions** → **Create Resource**
2. **Resource name:** `login` → **Create Resource**

![Create login resource](/images/workshop/AG4.png)

3. Select `/login` → **Actions** → **Create Method** → **POST** → ✓
4. Configure:
   - **Integration type:** Lambda Function
   - **Lambda proxy integration:** ✓ (checked)
   - **Lambda function:** `loginFunction`

5. Click **Save** → **OK** to grant permission

![Create POST /login](/images/workshop/AG5.png)

### /songs resource

1. Select the root `/` → **Actions** → **Create Resource**
2. **Resource name:** `songs` → **Create Resource**
3. Select `/songs` → **Actions** → **Create Method** → **GET** → ✓
4. Configure:
   - **Integration type:** Lambda Function
   - **Lambda proxy integration:** ✓ (checked)
   - **Lambda function:** `getSongsFunction`

5. Click **Save** → **OK**

![Create GET /songs](/images/workshop/getsongapi.png)

---

## 3. Create Cognito Authorizer

This authorizer will validate the JWT token on every request to `GET /songs`.

1. In the left sidebar → **Authorizers** → **Create New Authorizer**
2. Configure:
   - **Name:** `CognitoAuthorizer`
   - **Type:** Cognito
   - **Cognito User Pool:** select `workshop-pool`
   - **Token source:** `Authorization`

![Create Cognito Authorizer](/images/workshop/auth1.png)
![Create Cognito Authorizer](/images/workshop/auth2.png)
![Create Cognito Authorizer](/images/workshop/auth3.png)

3. Click **Create**
4. Click **Test** → enter the `idToken` from a login call → verify it returns `200`

---

## 4. Attach the Authorizer to GET /songs

1. Click on `/songs` → **GET** method
2. Click **Method Request**
3. Under **Authorization**, select `CognitoAuthorizer` from the dropdown
4. Click the ✓ checkmark to save

![Attach authorizer](/images/workshop/meth1.png)
![Attach authorizer result](/images/workshop/meth42.png)

Now `GET /songs` requires a valid JWT token. `POST /login` remains public.

---

## 5. Enable CORS

For each resource (`/login` and `/songs`):

1. Select the resource → **Actions** → **Enable CORS**
2. Keep defaults → **Enable CORS and replace existing CORS headers** → **Yes**

![Enable CORS](/images/workshop/cors1.png)
![Enable CORS confirm](/images/workshop/cors2.png)

---

## 6. Deploy the API

1. **Actions** → **Deploy API**
2. Configure:
   - **Deployment stage:** [New Stage]
   - **Stage name:** `dev`

![Deploy API](/images/workshop/AG7.png)

3. Click **Deploy**
4. Copy the **Invoke URL** — it looks like:
   `https://xxxxxxxxxx.execute-api.us-east-1.amazonaws.com/dev`

{{% notice info %}}
Save this URL. You will use it in the Testing section.
{{% /notice %}}
