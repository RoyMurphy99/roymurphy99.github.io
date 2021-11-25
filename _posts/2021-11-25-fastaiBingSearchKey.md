# Getting Bing Search Key and using it in fastai

The deep learning for coders book chapter 2 requires you to collect image data, to be used to train and evaluate a model or classiying images. 
To get the images, the book suggests using the Bing image search API, which requires a Bing image search key, and a Bing image search function. 

Getting the search key has changed over the last few years, so you see a lot of out of date instructions. As of now (25/11/2021), you have to get a microsoft
account. You use the same credentials (id and password) to log in to microsoft Azure Portal. After signing in,go to the following address in the browser
address bar: "microsoft.com/en-us/bing/apis/bing-image-search-api" then click "try now". From there I was able to select a pricing tier (I used the Free
tier), create a resource, then a resource group within that, then create/manage keys. 

To get the chapter 2 notebook to work properly, I had to copy in the following function definition into a code cell just ater the fastai import cells,
this function was not written by me but was published on one of the posts on the fastai forums:

def search_images_bing(key, term, max_images: int = 100, **kwargs):  

    params = {'q':term, 'count':max_images}  
    
    headers = {"Ocp-Apim-Subscription-Key":key}  
    
    search_url = "https://api.bing.microsoft.com/v7.0/images/search"  
    
    response = requests.get(search_url, headers=headers, params=params)  
    
    response.raise_for_status()  
    
    search_results = response.json()  
    
    return L(search_results['value'])  
    
    
I presume the search_images_bing() function supplied with fastai is not compatibile with the latest version of the API, but the above function
worked when I used it today. 
