import random

answers = ['Бесспорно', 'Мне кажется - да',	'Пока неясно, попробуй снова', 'Даже не думай',
'Предрешено',	'Вероятнее всего',	'Спроси позже',	'Мой ответ - нет',
'Никаких сомнений',	'Хорошие перспективы',	'Лучше не рассказывать',	'По моим данным - нет',
'Определённо да',	'Знаки говорят - да',	'Сейчас нельзя предсказать',	'Перспективы не очень хорошие',
'Можешь быть уверен в этом',	'Да',	'Сконцентрируйся и спроси опять',	'Весьма сомнительно'] # Заголовок программы

print('Привет Мир, я магический шар, и я знаю ответ на любой твой вопрос.')
print('Введите свое имя')

def is_valid(n):
    return n.isalpha()
    
def input_name(name):
    name = input()
    if is_valid(name):
        print('Привет', name)
    else:
        name = input('Введите имя состояших из букв')
        
def is_valid_ans(ans):
    return ans.isalnum()
    
def continue_game():
    print('хочете ли вы задать еще один вопрос')
    ans = input()
    if ans == 'да':
        return True
    elif ans == 'нет':
        print('Возвращайся если возникнут вопросы!')
        return False
    else:
        print('Ответте на вопрос да или нет')
        ans = input()
    
def game(): # Основной цикл программы
    name = input_name('nm')
    while True:
        print('Задайте вопрос магическому шару')
        answer = input()
        if is_valid_ans(answer):
            print(random.choice(answers))
        else:
            answer = input('Введите вопрос состояших из букв и цифр')
        if continue_game():
            continue
        else:
            break
    
game()
