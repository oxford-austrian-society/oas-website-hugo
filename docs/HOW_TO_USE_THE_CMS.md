# How to use the CMS to generate new posts

## 1.) Login

Go to **[Prose.io](http://prose.io)** and login with our github account.

## 2.) Folders and finding your way around

The first thing you'll see after logging in, is an overview of our projects.

Via the CMS, you can only edit folders that contains editable content, but no structurally important parts.
Thus, the folder `oxford-austrian-society.github.io` is empty; in the folder `oas-website-hugo` is editable.

To edit existing posts, or publish new ones, first click on `oas-website-hugo`.

## 3) 6 Steps to publishing a new post

Let's create a new post! First click on **blog**, then press the **NEW FILE**-button at the top of the page.

![Prose New Post](https://github.com/oxford-austrian-society/oas-website-hugo/blob/master/docs/img/prose-input-mask.png)

1. **Enter title of the post**: At the very top of the form, there is a field that displays **Untitled**. Edit this field to set a new title for the post. This title will be used to automatically name the file that you are generating. If your post is first generated on 2016-01-01, and is called **Update: This is my new post**, the resulting file will be called **2016-01-01-update-this-is-my-new-post.md**

2. **Write and format content**: Every new file comes with some dummy text. Delete it and start writing. To format, just use the buttons or click on the **?**-button to find out how to achieve more difficult formatting tasks. Importantly, this section will disply the raw markdown-syntax. If you want to learn more about how markdown works in general, read [Github's documentation](https://help.github.com/articles/basic-writing-and-formatting-syntax/).

3. **Preview your post**: To check whether your formatting is interpreted correctly, press the **Preview-button** (the one with the eye) on the right hand side of the page. This will not display the contents as they will be rendered on the website, but markdown formatting will be interpreted and rendered, i.e. headers will appear large and bold, links will be highlighted...

4. **IMPORTANT!!! Review/ Update metadata**: click on the **Metadata-button** (below the preview-button). This will take you to a page with an input form.
  - Make sure to select at least one tag under **Add tags**, some common ones are already preconfigured.
  - Do not forget to **add a date to the post**, otherwise, it will not appear in order on the website.
  - If you have a feature-image for your post, provide it's name under **Header Image**, and a description in the field below. Specify the path to your image under **full image path**. If the path to your image is `static/images/my-image.jpg`, the use `my-image.jpg` under **Header image**, and `/images/` under **full image path**
  (See below for how to upload an image...)
  - **Finally, confirm by clicking done**

  ![Metadata](https://github.com/oxford-austrian-society/oas-website-hugo/blob/master/docs/img/prose-metadata.png)

5. **Save changes**: Click on the **Save** button. The site will give you a summary of the changes to the post. Ideally, write an informative description of what you changed in the field above the **Commit-button**, then click it to save your changes.

![Saving](https://github.com/oxford-austrian-society/oas-website-hugo/blob/master/docs/img/prose-save.png)

6. **Publish**: after commiting your changes, you are taken back to the editor view. Refresh your page, and a button displaying **Unpublished** will appear to the right just above your text. Click on it, and it will switch to **Published**. Finally, click on **save changes**, and **commit** again.

## 4.) Uploading images

Unfortunately, there's only one way to upload images in the CMS, and that is to upload one, while editing a post.
Click on the **image-button** in the toolbar.

![Image upload](https://github.com/oxford-austrian-society/oas-website-hugo/blob/master/docs/img/prose-image.png)

A box will appear, which has two sections:

- **Right: Choose an existing image.** Here, you'll find a list of all images that are stored in the dedicated image folder. Select one by clicking on it. This will fill out the form for you with the right variables. Click **Insert** to insert the image to the main body of your post.

- **Left: Upload a new image.** Click on **selecting one**, and a dialogue will appear allowing you to select a picture from your local files. If you select **my-image.jpg** on your computer, and confirm the upload, the first line in the form will now display `static/images/my-image.jpg`. Click **Insert** to insert the image to the main body of your post.

In any case, clicking **Insert** will result in the following line being added to your text:

```
![my-image.jpg]({{site.baseurl}}/static/images/my-image.jpg)
```
If you want to leave the image in the body of the text, that's it. Just save and commit your changes, and and publish the post.

In case you don't want to use the image in the body, but rather as a feature image (which looks a bit better in my opinion), just delete the line of code above, go to the the **Metadata-section**, and fill out the form as described above in *3-4*.
