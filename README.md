# Ovsiyenko_lab9

#include <iostream>
#include <string>
#include <vector>

struct Book {
    std::string title, author, genre;
    int year;
};

std::vector<Book> filterBooksByYear(const std::vector<Book>& books, int year) {
    std::vector<Book> filteredBooks;
    for (const auto& book : books) {
        if (book.year >= year) {
            filteredBooks.push_back(book);
        }
    }
    return filteredBooks;
}

int main() {
    std::vector<Book> books = {
        {"Над прірвою в житті", "Дж. Д. Селінджер", "Художня література", 1951},
        {"Убити пересмішника", "Харпер Лі", "Художня література", 1960},
        {"1984", "Джордж Орвелл", "Дистопія", 1949},
        {"Мобі Дік", "Герман Мелвілл", "Пригода", 1851},
        {"Прекрасний новий світ", "Олдос Хакслі", "Дистопія", 1932}
    };

int yearThreshold;
    
    std::cout << "Введіть поріг року: ";
    std::cin >> yearThreshold;

    std::vector<Book> filteredBooks = filterBooksByYear(books, yearThreshold);

    std::cout << std::endl << "Книги, видані після або в " << yearThreshold << " році:" << std::endl;
    for (const auto& book : filteredBooks) {
        std::cout << book.title << " автор: " << book.author << ", рік: " << book.year << ", жанр: " << book.genre << std::endl;
    }

    return 0;
}
