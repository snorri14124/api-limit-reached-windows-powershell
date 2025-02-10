# api-limit-reached-windows-powershell
How to avoid the GitHub API rate limit error windows powershell





If you're getting the "API rate limit exceeded" or "Bad credentials" errors when using the GitHub API for Spicetify, here's how you can resolve it:

Generate a GitHub Personal Access Token (PAT)

Go to GitHub Personal Access Tokens.
Click "Generate new token" and ensure you select the "public_repo" permission (this is all you need).
Copy the token immediately as you won't see it again.

replace YOUR_GITHUB_TOKEN with the token you got from the explanation over

$headers = @{ Authorization = "token YOUR_GITHUB_TOKEN" }
Invoke-RestMethod -Uri "https://api.github.com/repos/spicetify/spicetify-cli/releases/latest" -Headers $headers
Replace YOUR_GITHUB_TOKEN with the token you generated.

then you just paste that into windows powershell after you put the token into

Why this works
GitHub limits unauthenticated requests to 60 per hour per IP. However, when you use an authenticated request, the limit increases to 5,000 requests per hour. This means you can make many more requests without hitting the limit.

Rate Limit Reset
The limit resets every hour. If you reach the limit, just wait for one hour, and you'll be able to continue making requests.

Note: If you still see errors, double-check your token for correct permissions and ensure that your request format is valid.

Now you can make more requests without hitting the limit! 😊


"(if that didn't work then try pasting it into chat gpt and let that correct it then it should work)"
