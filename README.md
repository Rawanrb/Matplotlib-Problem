# Matplotlib-Problem
To solve the backend problem with matplotlib
I have faced a problem while I am trying to plt with matplotlib that the Matplotlib is currently using agg, which is a non-GUI backend, so cannot show the figure.

I found this code would help to figure out the right backend for your current system. The solution was taken from:

https://stackoverflow.com/questions/8650957/matplotlib-no-object-use-or-version

Just simply in a separate file run the following code:

import matplotlib
gui_env = [i for i in matplotlib.rcsetup.interactive_bk]
non_gui_backends = matplotlib.rcsetup.non_interactive_bk
print ("Non Gui backends are:", non_gui_backends)
print ("Gui backends I will test for", gui_env)
for gui in gui_env:
    print ("testing", gui)
    try:
        matplotlib.use(gui,warn=False, force=True)
        from matplotlib import pyplot as plt
        print ("    ",gui, "Is Available")
        plt.plot([1.5,2.0,2.5])
        fig = plt.gcf()
        fig.suptitle(gui)
        plt.show()
        print ("Using ..... ",matplotlib.get_backend())
    except:
        print ("    ",gui, "Not found")

Attached a file with the same code.

Once the system told you the right backend so every time you use matplotlib:

use the following:

import matplotlib
matplotlib.use('Name_of_the_backend_given_by_previous_code')

Hopefully, this would help :)

