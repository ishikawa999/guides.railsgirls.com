---
layout: main_guide
title: Build your first app
permalink: app
---

# Build your first app

*Originally created by Vesa Vänskä, [@vesan](https://twitter.com/vesan)*

{% include main-guide-intro.html %}

## Important

It is important that you select the instructions specific to your operating system - the commands you need to run on a Windows computer are slightly different to Mac or Linux. If you're having trouble check the Operating System switcher at the bottom of the commands. In case you're using a cloud service (e.g. Replit), you need to run the Linux commands even if you are on a Windows computer.

## Creating the application

We're going to create a new Rails app called *railsgirls*.

First, open the Terminal app and type in these commands:

<div class="os-specific">
  <div class="mac nix">
{% highlight sh %}
mkdir projects
{% endhighlight %}

    <div>
<p>You can verify that a directory named <code>projects</code> was created by running the list command: <code>ls</code>. You should see the <code>projects</code> directory in the output. Now you want to change the directory you are currently in to the <code>projects</code> folder by running:</p>
    </div>

{% highlight sh %}
cd projects
{% endhighlight %}

    <div>
<p>You can verify you are now in an empty directory or folder by again running the <code>ls</code> command. Now you want to create a new app called <code>railsgirls</code> by running:</p>
    </div>

{% highlight sh %}
rails new railsgirls
{% endhighlight %}

    <div>
<p>This will create a new app in the folder <code>railsgirls</code>, so we again want to change the directory to be inside of our rails app by running:</p>
    </div>

{% highlight sh %}
cd railsgirls
{% endhighlight %}

    <div>
<p>If you run <code>ls</code> inside of the directory you should see folders such as <code>app</code> and <code>config</code>. You can then start the rails server by running:</p>
    </div>

{% highlight sh %}
rails server
{% endhighlight %}
  </div>

  <div class="win">
{% highlight sh %}
mkdir projects
{% endhighlight %}

    <div>
<p>You can verify that a directory named <code>projects</code> was created by running the list command: <code>dir</code>. You should see the <code>projects</code> directory in the output. Now you want to change the directory you are currently in to the <code>projects</code> folder by running:</p>
    </div>

{% highlight sh %}
cd projects
{% endhighlight %}

    <div>
<p>You can verify you are now in an empty directory or folder by again running the <code>dir</code> command. Now you want to create a new app called <code>railsgirls</code> by running:</p>
    </div>

{% highlight sh %}
rails new railsgirls
{% endhighlight %}

    <div>
<p>This will create a new app in the folder <code>railsgirls</code>, so we again want to change the directory to be inside of our rails app by running:</p>
    </div>

{% highlight sh %}
cd railsgirls
{% endhighlight %}

    <div>
<p>If you run <code>dir</code> inside of the directory you should see folders such as <code>app</code> and <code>config</code>. You can then start the rails server by running:</p>
    </div>

{% highlight sh %}
rails server
{% endhighlight %}
  </div>
</div>

Open <http://localhost:3000> in your browser. If you are using a cloud service (e.g. Replit), use its preview functionality instead (see [installation guide](/install/replit) for details).

You should see a page with the Rails logo, which means that your Rails app is up and running.

Notice in the Terminal window the command prompt is not visible because you are now in the Rails server. The command prompt will look something like this, but it may be different on your laptop:

<div class="os-specific">
  <div class="mac nix">
{% highlight sh %}
$
{% endhighlight %}
  </div>
  <div class="win">
{% highlight sh %}
>
{% endhighlight %}
  </div>
</div>

When the command prompt is not visible you cannot execute new commands. If you try running `cd` or another command it will not work. To stop the Rails server and return to the normal command prompt in the same Terminal window, press <kbd>Ctrl</kbd>+<kbd>C</kbd> in the Terminal to quit the Rails server.

{% coach %}
Explain what each command does. What was generated? What does the server do?
{% endcoach %}

## Create Idea scaffold

We're going to use Rails' scaffold functionality to generate a starting point that allows us to list, add, remove, edit, and view things; in our case ideas.

{% coach %}
What is Rails scaffolding? (Explain the command, the model name and related database table, naming conventions, attributes and types, etc.) What are migrations and why do you need them?
{% endcoach %}

{% highlight sh %}
rails generate scaffold idea name:string description:text picture:string
{% endhighlight %}

The scaffold creates new files in your project directory, but to get it to work properly we need to run a couple of other commands to update our database and restart the server.

{% highlight sh %}
rails db:migrate
rails server
{% endhighlight %}

Open <http://localhost:3000/ideas> in your browser. Cloud service (e.g. Replit) users need to append `/ideas` to their preview URL instead (see [installation guide](/install/replit)).

Click around and test what you got by running these few command-line commands. You should be able to make new ideas, view, edit and delete (destroy) them.

## Finetune the routes

Open <http://localhost:3000> (or your preview URL). It will show a page with only the Rails logo. Let's make it redirect to the ideas page instead.

Open the `config/routes.rb` file in your Text Editor. After the first line, add this line and save it:

{% highlight ruby %}
root to: redirect("/ideas")
{% endhighlight %}

Test the change by opening the root path (that is, <http://localhost:3000/> or your preview URL) in your browser. It should now open the ideas index page when you visit the root path. The URL in the Browser's address bar should have automatically changed to <http://localhost:3000/ideas>.

{% coach %}
Talk about routes, and include details on the order of routes and their relation to static files.
{% endcoach %}

## Next steps

You have now created your first app! Congratulations!

From here we will continueing working on the app to improve the design with HTML and CSS, add more pages, add picture uploads, put your app online so that others can see it as well, share the code with others, allow people to leave comments, etc.

Talk with your coach about the steps you took in this guide. Do you have questions about any of the steps? Ask them before moving on to the next guide.