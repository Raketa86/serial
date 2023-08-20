class Сериал:
    def __init__(self, название, год_выхода, список_актеров, режиссер, жанр, сезоны):
        self.название = название
        self.год_выхода = год_выхода
        self.список_актеров = список_актеров
        self.режиссер = режиссер
        self.жанр = жанр
        self.сезоны = сезоны
        
class Сезон:
    def __init__(self, название, кол_серий, список_серий):
        self.название = название
        self.кол_серий = кол_серий
        self.список_серий = список_серий
        class СериалService:
        
    def __init__(self):
        self.сериалы = []
        self.любимые_сериалы = []
        self.любимые_сезоны = []
        self.любимые_серии = []

    def получить_общий_список_сериалов(self):
        return self.сериалы

    def добавить_сериал_в_любимые(self, сериал):
        self.любимые_сериалы.append(сериал)

    def добавить_сезон_в_любимые(self, сезон):
        self.любимые_сезоны.append(сезон)

    def добавить_серию_в_любимые(self, серия):
        self.любимые_серии.append(серия)

    def поиск_по_номеру_серии(self, номер):
        результаты = []
        for сериал in self.сериалы:
            for сезон in сериал.сезоны:
                for серия in сезон.список_серий:
                    if серия.номер == номер:
                        результаты.append(серия)
        return результаты

    def поиск_по_названию_сезонов(self, название_сезона):
        результаты = []
        for сериал in self.сериалы:
            for сезон in сериал.сезоны:
                if сезон.название == название_сезона:
                    результаты.append(сезон)
        return результаты

    def поиск_по_названию_сериалов(self, название_сериала):
        результаты = []
        for сериал in self.сериалы:
            if сериал.название == название_сериала:
                результаты.append(сериал)
        return результаты

        сериал_service = СериалService()

сериал1 = Сериал("Friends", 1994, ["Дженнифер Энистон", "Коуртни Кокс"], "Джеймс Берроуз", "комедия", [
    Сезон("Сезон 1", 24, []),
    Сезон("Сезон 2", 24, [])
])
сериал_service.сериалы.append(сериал1)

любимый_сезон = сериал1.сезоны[0]
сериал_service.добавить_сезон_в_любимые(любимый_сезон)

любимая_серия = любимый_сезон.список_серий[0]
сериал_service.добавить_серию_в_любимые(любимая_серия)

поиск_по_номеру_серии = сериал_service.поиск_по_номеру_серии(1)
поиск_по_названию_сезона = сериал_service.поиск_по_названию_сезонов("Сезон 1")
поиск_по_названию_сериала = сериал_service.поиск_по_названию_сериалов("Friends")
