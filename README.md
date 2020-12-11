# chinese-calligraphy-classifier-fastai

**Chinese Calligraphy Classifier using fast.ai**


## Overview
Like any calligraphy, Chinese calligraphy is a form of art. Some great pieces written by some ancient masters have both great art value and economic values (selling at multi-million dollars on auctions).

![*Jieshi Tie* by Song Dynasty politician and scholar Zeng Gong, $30,000,000](https://cdn-images-1.medium.com/max/2000/1*2lrTyRMYIcm6HfnojdgUvg.jpeg)\*_Jieshi Tie_ by Song Dynasty politician and scholar Zeng Gong, \$30,000,000\*

There are multiple main styles/schools of calligraphy, mainly belongs to different dynasties. Each has its own way of shaping the character and arranging them. The differences are subtle and abstract. It makes sense to see if a trained deep learning model can do a good job of telling which style it is.

I picked three styles:

- Lishu(隶书)

- Kaishu(楷书)

- Xiaozhuan(小篆)

as a proof-of-concept. Once successful trained, the model could serve as a transfer learning base-model for the more fine-grained classifier( e.g. calligraphers classifier). This has some real-life value. From time to time, some ancient artifacts are discovered and some of them are calligraphy artworks. Sometimes it’s hard to tell whose work it is. Is it valuable (like undiscovered artwork by a famous calligrapher)?

> This calligrapher classifier can serve as a way to quickly identify artworks by great calligraphers. ( Finding diamond in the rough _😉_)

## Data Collection
To build a calligraphy classifier, we will need some calligraphy examples of each style. I did some search online and cannot find any good already-made data-set for different calligraphy styles. So I’ll have to build it myself.

Building a images data-set isn’t hard thanks to Google’s Images search functionality and some JavaScript snippets. Here’s how:

1. Go to [Google Images](https://www.google.com/imghp?hl=en) and search for “隶书 字帖 网格” (lishu, characters book, grid), this will give you the most relevant results.

1. Scroll down to show more results, you’ll hit the bottom with ‘_Show more results_’ button. Click if you want more, but keep in mind that **700** images is the maximum here.

![Google search results for Lishu style](https://cdn-images-1.medium.com/max/2000/1*uQPNDb-qXO3mYQIHuxitMQ.png)_Google search results for Lishu style_

3. Now is where the magic happens. Press Ctrl+Shift+J in Windows/Linux and Cmd+Opt+J in Mac to bring up the JavaScript ‘Console’ window of the browser. The following JavaScript snippet will get the URLs of each of the images.

4) If successfully run, a text file will be downloaded with all the URLs for the images in your search results. You can then set up a folder and use fast.ai’s ‘download_images’ function to download these images.

![](https://cdn-images-1.medium.com/max/2000/1*19mOhygnBZfGmX4S2fD4ww.png)

5. Rinse and repeat for other styles. You might want to put them into different folders like kaishu, xiaozhuan and put them all under a folder called train so later on, fast.ai can easily import them into the model.

6. Alternatively, you can also go to Baidu.com for images search, using this [snippet](https://gist.github.com/wayofnumbers/39842bb909c04070de49e53c418d512f) to automatically download the images you searched for.


## Notebook and Dataset
You can find the full **Jupyter Notebook** ![here](https://github.com/wayofnumbers/chinese-calligraphy-classifier-fastai/blob/main/chinese-calligraphy-classifier-using-fast-ai.ipynb)
Dataset ![here](https://github.com/wayofnumbers/chinese-calligraphy-classifier-fastai/tree/main/data)


## Articles
I wrote two articles about this project on Medium.com, which you can find below:
![How I Trained Computer to Learn Calligraphy Styles: Part1](https://medium.com/datadriveninvestor/deep-learning-models-by-fast-ai-library-c1cccc13e2b3?source=friends_link&sk=a1418f68abb99b5c9ee0e18d0873bff7), ![Part 2](https://medium.com/datadriveninvestor/chinese-calligraphy-classifier-fine-tuning-cbfbf0e304d8?source=friends_link&sk=51d895caada37a46f90971596cfd5672)


## Snippets
Python scripts to download the searched images from Baidu can be found ![here](https://github.com/wayofnumbers/chinese-calligraphy-classifier-fastai/blob/main/scripts/collect_images_from_baidu_search_results.py)


## Web app and Deployment
(coming...)

