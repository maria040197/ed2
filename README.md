# ed2
Tarv* buscaArv (Tarv* arv, char ch){

    if(arv == NULL){
        return NULL;
    }else if(arv->dado == ch){
        return arv;    
    }else if(arv->dado < ch){
         buscaArv(arv->esq, ch);        
    }else{
         buscaArv(arv->dir, ch);
    }
    
    return arv;
}
int percenceArv(Tarv* arv, char ch){
    if(arv == NULL){
        return 0;
    }else if(arv->dado == ch){
        return 1;
    }else if(arv->dado < ch){
        percenceArv(arv->esq, ch);
      
    }else{
       percenceArv(arv->dir, ch);
    }
    
     return 1;
}
Tarv* removeArv(Tarv* arv, char ch){
    Tarv *aux;
    
    if(arv == NULL){
        return NULL;
    }else if(arv->dado < ch){
        arv->esq = removeArv(arv->esq, ch)
    }else if(arv->dado > ch){
        arv->dir = removeArv(arv->dir, ch);
    }else{ // achou a arv que quer excluir
        if(arv->esq == NULL || arv->dir == NULL){ // arv não tem filhos
            free(arv);
            arv == NULL;
        }else if(arv->esq == NULL){ // arv com filho somente a direita
            aux = arv;
            arv->dir = aux;
            free(aux);
        }else if(arv->dir == NULL){ // arv com filho somente a esquerda
            aux = arv;
            arv->esq = aux;
            free(aux);
        }else{ // arv com filho em cada lado
            
            
            
        }
    }
}

