# Software-Testing-Assignment-No-02
TEST CASES FOR BOOK STORE APPLICATION USING CYPRESS.IO FRAMEWORK:
TEST CASES FOR BOOK STORE APPLICATION USING CYPRESS.IO FRAMEWORK:

describe('Webpage Tests', () => {
  beforeEach(() => {
    cy.visit('http://localhost:3000');
  });
  it('Should display the homepage', () => {
    cy.contains('Books List');
  });

  context('Navigation', () => {
    it('Should navigate to Create Book page', () => {
      cy.contains('Create Book').click();
      cy.url().should('include', '/books/create');
    });

    it('Should navigate to Show Book page', () => {
      cy.get('.book-link').first().click();
      cy.url().should('include', '/books/details/');
    });

    it('Should navigate to Edit Book page', () => {
      cy.get('.edit-book-link').first().click();
      cy.url().should('include', '/books/edit/');
    });

    it('Should navigate to Delete Book page', () => {
      cy.get('.delete-book-link').first().click();
      cy.url().should('include', '/books/delete/');
    });
  });

  context('Create Book', () => {
    it('Should create a new book', () => {
    });
  });

  context('Show Book', () => {
    it('Should display book details', () => {
            cy.get('.book-link').first().click()
    });
  });

  context('Edit Book', () => {
    it('Should edit an existing book', () => {
      cy.get('.edit-book-link').first().click();
    });
  });

  context('Delete Book', () => {
    it('Should delete an existing book', () => {
      cy.get('.delete-book-link').first().click();
    });
  });

  context('Login', () => {
    it('Should login successfully', () => {
    });
  });

  context('Search', () => {
    it('Should search for a book', () => {
    });
  });

context('User Authentication', () => {
  it('Should display an error message for invalid login', () => {
    cy.contains('Invalid credentials');
  });

  it('Should redirect to the login page for unauthorized access', () => {
    cy.visit('http://localhost:3000/books/create');
    
    cy.url().should('include', '/login');
  });

  it('Should log in and log out successfully', () => {
    cy.contains('Welcome, [username]');
    cy.contains('Logout').click()
    cy.url().should('include', '/login');
  });
});

context('Search', () => {
  it('Should display "No results found" for an invalid search query', () => {
    cy.contains('No results found');
  });

  it('Should filter books based on the search query', () => {
    cy.get('.book-title').each((bookTitle) => {
      expect(bookTitle.text()).to.include('searchQuery');
    });
  });
});


});

