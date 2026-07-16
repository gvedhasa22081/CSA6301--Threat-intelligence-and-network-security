<img width="897" height="591" alt="image" src="https://github.com/user-attachments/assets/299f7d66-6cb6-4713-87ed-918076bc818e" />
from urllib.parse import urlparse
import re

def check_phishing(url):
    score = 0

    # Check if URL contains an IP address
    if re.search(r'\d+\.\d+\.\d+\.\d+', url):
        print("IP address found in URL")
        score += 1

    # Check for @ symbol
    if "@" in url:
        print("@ symbol found")
        score += 1

    # Check URL length
    if len(url) > 75:
        print("URL is too long")
        score += 1

    # Check for multiple hyphens
    if url.count("-") > 2:
        print("Too many hyphens")
        score += 1

    # Check for suspicious keywords
    suspicious_words = ["login", "verify", "update", "bank", "secure", "account"]

    for word in suspicious_words:
        if word in url.lower():
            print(f"Suspicious keyword found: {word}")
            score += 1

    # Final result
    if score >= 2:
        print("\nResult: Likely Phishing URL")
    else:
        print("\nResult: URL appears Safe")

# Main Program
url = input("Enter a URL: ")
check_phishing(url)
