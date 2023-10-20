from telegram import Update
from telegram.ext import Updater, MessageHandler, CallbackContext, Filters, Dispatcher


TOKEN = "6444878628:AAHhHLnDi5e43Jruh6c72xejk5otZ1bD8fk"



def main():
    updater = Updater(token=TOKEN)
    dispatcher: Dispatcher = updater.dispatcher

    echo_handler = MessageHandler(Filters.text, do_echo)

    dispather.add_handler(echo_handler)

    updater.start_polling()
    print(updater.bet.getMe())
    updater.idle()


def do_echo(update: Update, context: CallbackContext):
    user_id = update.message.from_user.id
    username = update.message.from_user.username
    text  = update.message.text

    print(f'{username} {user_id} вызвал функцию echo')
    answer = f"Твой {user_id=}\nТвой {username=}\n {text}"

    update.message.reply_text(answer)
   
