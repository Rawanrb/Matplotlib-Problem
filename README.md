# Matplotlib-Problem
To solve the backend problem with matplotlib
I have faced a problem while I am trying to plt with matplotlib that the Matplotlib is currently using agg, which is a non-GUI backend, so cannot show the figure.

I found this code would help to figure out the right backend for your current system. The solution was taken from:

https://stackoverflow.com/questions/8650957/matplotlib-no-object-use-or-version

Just simply run the attached a file (mat.py)

Once the system told you the right backend so every time you use matplotlib:

use the following:

import matplotlib

matplotlib.use('Name_of_the_backend_given_by_previous_code')

Hopefully, this would help :)

