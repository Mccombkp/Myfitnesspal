A daily email report that aggregates nutritional data from Myfitnesspal and adds a few metrics that Myfitnesspal choose not to add. While I find their in-app dashboards great for looking at a day to day basis, I was disappointed with what their app offered in the way of tracking nutrition over longer periods.

So I created this simple yet great email report using python and Jupyter Notebook to add week by week and 7-day rolling metrics that can help one losing weight make better inferences on their progress beyond looking at a scale.

For me, this helped me optimize my meal preps based on a weekly rather than a daily view to help me fulfill my caloric and macro nutritional needs. It also helped me figure out when I can have my "cheat meals" and not have to worry about gaining any weight.

Credit to [Coddingtonbear](https://github.com/coddingtonbear/python-myfitnesspal) for creating this python package.

Requirements
------------

Along with the standard packages that are included with Python, this project uses the following Python libraries

```python
pip install plotly
pip install python-pptx
```

Personalizing
------------
Change the following variables to match your Myfitnesspal login information as well as the login information from the email address that will email the report to yourself.

```python
client = mfp.Client(USERNAME, PASSWORD)
```

```python
EMAIL_ADDRESS = sender_email_address
PASSWORD = EMAIL_PASSWORD
receiver_email = reciever_email_address
```

Automate Reporting
------------

The best way to take advantage of script is to run it on a headless server to send out on a daily basis.

For beginners, you can check out [this article](https://towardsdatascience.com/running-jupyter-notebook-in-google-cloud-platform-in-15-min-61e16da34d52) to help you get set up.


A few things to note though is that setup for Plotly Orca, which saves the plotly charts as a .png, is a little different on Ubuntu.

Here are a few steps to take when downloading it:

1:) Download [latest app image](https://github.com/plotly/orca/releases/download/v1.3.1/orca-1.3.1.AppImage) from [here](https://github.com/plotly/orca).

2:) within the ubuntu terminal, make the file executable with chmod a+rx path/to/orca
  
3:) Finally, execute the file: xfvb run app image
