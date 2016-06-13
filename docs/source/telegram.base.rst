telegram.base module
====================

.. automodule:: telegram.base
    :members:
    :undoc-members:
    :show-inheritance:
    import telegram
bot = telegram.Bot(token='238623519:AAF_pZtzuYM2iiMvLUfC9vi3MBrwfv2tqKo')
@app.route('/<238623519:AAF_pZtzuYM2iiMvLUfC9vi3MBrwfv2tqKo>', methods=['POST'])
def launcher(token):
    if request.method == "POST":
        update = telegram.Update.de_json(request.get_json(force=True))
        handle_message(update.message)
    return 'ok'

def handle_message(message):
    text = message.text
    if '/echo' in text:
        echo(message)
    elif '/milestone' in text:
        milestone(message)
    elif '/help' in text:
        help(message)
    elif '/getmylastat' in text:
        get_my_last_at(message)
    elif '/pic' in text:
        pic(message)
    elif '/delpic' in text:
        delpic(message)

    if not '/' in text and '@' in text:
        save_at_message(message)
        
