# Image Posting Automation with AI-Generated Captions (Instagram & Facebook)

This Python script automates the process of posting images to Instagram and Facebook with captions generated by **BLIP (Bootstrapping Language-Image Pretraining)** model. It leverages the **Imgur API** to upload images and retrieves the public URLs for posting on social media platforms. You can specify a folder with images, and the script will generate captions, upload them, and post them at a user-defined time interval. This is ideal for users managing multiple accounts and looking to automate social media posts.

---

## Features

- **AI-Powered Captions**: Uses the **BLIP model** from Hugging Face Transformers to generate natural and contextually relevant captions for the images.
- **Instagram and Facebook Integration**: Automatically posts images to both **Instagram** and **Facebook** using their respective Graph API.
- **Imgur Hosting**: Uploads images to **Imgur**, allowing publicly accessible URLs that are used for posting on social media.
- **Multiple Image Posting**: Automates the posting of multiple images from a specified folder.
- **Configurable Time Interval**: Allows you to define a time interval between posts, ensuring regular updates without manual intervention.
- **Seamless Integration**: Combines the power of API interactions and AI to streamline social media management.

---

## Requirements

1. Python 3.x
2. Required Python Libraries:
    - `transformers`
    - `requests`
    - `Pillow`
    - `time`
    - `os`

Install the dependencies using:
```bash
pip install transformers requests Pillow
```

3. Instagram & Facebook API Access:
    - Obtain an **Access Token** for your Instagram account and Facebook page using the [Facebook Developer](https://developers.facebook.com/) platform.
    - **Imgur Client ID** for uploading images to Imgur.

---

## Setup

### Step 1: Get API Credentials

#### Instagram & Facebook Access Tokens
- Generate an **Instagram Access Token** for the account you want to post to.
- Generate a **Facebook Access Token** and retrieve the **Facebook Page ID** where you want to post.

#### Imgur Client ID
- Create an Imgur account and register a new application to get your **Client ID** from [Imgur API](https://apidocs.imgur.com/).

### Step 2: Add Credentials to the Code

In the script, replace the placeholders with your own credentials:

```python
instagram_access_token = "<YOUR_INSTAGRAM_ACCESS_TOKEN>"
instagram_account_id = "<YOUR_INSTAGRAM_ACCOUNT_ID>"
facebook_access_token = "<YOUR_FACEBOOK_ACCESS_TOKEN>"
facebook_page_id = "<YOUR_FACEBOOK_PAGE_ID>"
imgur_client_id = "<YOUR_IMGUR_CLIENT_ID>"
```

### Step 3: Set Folder Paths
- Set the folder path that contains the images you want to post.
- For example:
  ```python
  folder_path = '/path/to/your/images'  # Path to folder containing the images
  time_interval = 240  # Time interval in seconds (e.g., 4 minutes)
  ```

---

## How It Works

1. **Generate Captions**: For each image in the specified folder, the BLIP model generates a caption based on the content of the image.
   
2. **Upload to Imgur**: Each image is uploaded to Imgur to obtain a publicly accessible URL.

3. **Post to Instagram**: Using the Imgur URL and the generated caption, the script uploads the image to Instagram and publishes the post.

4. **Post to Facebook**: Similarly, the Imgur URL and the caption are posted to the Facebook page.

5. **Time Interval**: After posting an image, the script waits for the user-defined time interval (in seconds) before posting the next image.

---

## How to Use

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/image-posting-bot.git
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Replace the placeholders (`<YOUR_INSTAGRAM_ACCESS_TOKEN>`, etc.) with your API credentials.

4. Run the script:
   ```bash
   python post_to_socials.py
   ```

---

## Key Considerations

- **API Rate Limits**: Be mindful of Instagram, Facebook, and Imgur API rate limits.
- **Privacy**: Ensure your access tokens and sensitive information are kept secure.
- **Time Intervals**: Adjust `time_interval` based on your social media strategy to prevent spamming.

---

## Future Enhancements

- **Scheduled Posting**: Implement a scheduler to run the script at specific times of the day.
- **Hashtag Generation**: Automatically generate relevant hashtags for the post.
- **Support for Stories**: Extend the script to support Instagram Stories.
- **Enhanced Captioning**: Use more advanced models for generating detailed captions.
  
---

## License

This project is licensed under the MIT License.
